# Alternativas de Inicio

## Evolución Histórica

El sistema de inicio en Linux ha evolucionado significativamente desde sus inicios. El primer sistema de inicio ampliamente adoptado fue SysVinit (System V init), que se basaba en el sistema de inicio de Unix System V. Este sistema, aunque funcional, presentaba limitaciones significativas en los sistemas modernos.

## Limitaciones de SysVinit

SysVinit se ejecutaba como un proceso en serie dividido en una serie de etapas secuenciales (runlevels). Cada etapa requería finalización antes de que la siguiente pudiera continuar. Por lo tanto, el arranque no aprovechaba bien el parallel processing (procesamiento en paralelo) que podría hacerse en varios procesadores o núcleos.

Los runlevels en SysVinit (0-6) definían diferentes estados del sistema:
- 0: Apagado
- 1: Modo monousuario
- 2: Multiusuario sin red
- 3: Multiusuario con red (modo texto)
- 5: Multiusuario con red (modo gráfico)
- 6: Reinicio

Además, el apagado y el reinicio se consideraron un evento relativamente raro con lo que su duración no se consideró importante. Esto ya no es cierto, especialmente con los dispositivos móviles y los sistemas Linux integrados. Algunos métodos modernos, como el uso de containers (contenedores), pueden requerir tiempos de inicio casi instantáneos. Por lo tanto, los sistemas actuales requieren métodos con capacidades más rápidas y mejoradas. Por último, los métodos anteriores requerían scripts de inicio bastante complicados, que eran difíciles de mantener universales en todas las versiones de distribución, versiones del kernel, arquitecturas y tipos de sistemas.

## Alternativas Modernas

### Upstart
  
-   Desarrollado por Ubuntu e incluido por primera vez en 2006
-   Adoptado en Fedora 9 (en 2008) y en RHEL 6 y sus clones
-   Introdujo el concepto de eventos para iniciar servicios
-   Permitió cierto nivel de paralelización
-   Mejoró la gestión de dependencias entre servicios

### systemd

-   Adoptado por Fedora en primer lugar (en 2011)
-   Adoptado por RHEL 7 y SUSE
-   Upstart sustituido en Ubuntu 16.04
-   Se ha convertido en el estándar de facto en la mayoría de las distribuciones Linux modernas
   
Mientras que la migración a systemd generó bastante controversia, ha sido adoptado por todas las principales distribuciones. Independientemente de las controversias sobre los métodos técnicos de systemd, su adopción casi universal ha simplificado el aprendizaje de cómo trabajar en sistemas Linux, ya que hay menos diferencias entre las distribuciones. Una cosa a tener en cuenta es que **/sbin/init** ahora apunta a **/lib/systemd/systemd**; es decir, systemd se hace cargo del proceso init.

# Características de systemd

## Ventajas Principales

1. **Arranque Paralelo**: Los sistemas con systemd arrancan más rápido que los que tienen los primeros métodos init. Esto se debe en gran medida a que reemplaza un conjunto de pasos serializados por técnicas de paralelización agresivas, que permiten iniciar varios servicios simultáneamente.

2. **Configuración Simplificada**: Las complicadas secuencias de comandos de shell de inicio se reemplazan por archivos de configuración más sencillos (unit files), que enumeran:
   - Dependencias del servicio
   - Requisitos previos
   - Comandos de inicio
   - Condiciones de éxito
   - Comportamiento en caso de fallo

3. **Gestión de Dependencias**: systemd maneja automáticamente las dependencias entre servicios, asegurando que se inicien en el orden correcto.

4. **Sistema de Targets**: Reemplaza los runlevels tradicionales con un sistema más flexible de "targets" que pueden ser activados y desactivados dinámicamente.

## Comandos Básicos

Un comando systemd (**systemctl**) se utiliza para la mayoría de las tareas básicas. Aquí hay una lista más completa de su uso:

### Gestión de Servicios
```bash
# Iniciar, detener, reiniciar un servicio
$ sudo systemctl start|stop|restart httpd.service

# Habilitar o deshabilitar un servicio
$ sudo systemctl enable|disable httpd.service

# Ver el estado de un servicio
$ sudo systemctl status httpd.service

# Ver todos los servicios
$ sudo systemctl list-units --type=service
```

### Gestión de Targets
```bash
# Cambiar al modo gráfico
$ sudo systemctl isolate graphical.target

# Ver el target actual
$ sudo systemctl get-default

# Establecer el target por defecto
$ sudo systemctl set-default graphical.target
```

### Otras Funcionalidades Útiles
```bash
# Ver los logs de un servicio
$ sudo journalctl -u httpd.service

# Recargar la configuración de systemd
$ sudo systemctl daemon-reload

# Ver el tiempo de arranque
$ systemd-analyze
```

En la mayoría de los casos, el **.service** se puede omitir. systemd también maneja otros tipos de unidades como:
- .socket (para sockets de red)
- .mount (para puntos de montaje)
- .timer (para tareas programadas)
- .path (para monitoreo de archivos)

Estas mejoras han hecho que systemd sea no solo más rápido, sino también más robusto y fácil de mantener que sus predecesores.