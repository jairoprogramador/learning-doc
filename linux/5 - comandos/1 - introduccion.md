# Introducción a la línea de comandos

Los administradores de sistemas Linux pasan una gran parte de su tiempo en la línea de comandos. A menudo automatizan tareas y solucionan problemas en este entorno de texto. Hay un dicho, «las interfaces gráficas de usuario facilitan las tareas sencillas, mientras que las interfaces de línea de comandos hacen posibles tareas difíciles». Linux depende en gran medida de la abundancia de herramientas de línea de comandos. La interfaz de línea de comandos proporciona las siguientes ventajas:

- No se incurre en sobrecarga de la GUI.
- Prácticamente todas y cada una de las tareas se pueden llevar a cabo sentado en la línea de comandos.
- Puedes implementar scripts para tareas de uso frecuente (o fáciles de olvidar) y una serie de procedimientos.
- Puedes iniciar sesión en máquinas remotas en cualquier parte de Internet.
- Puedes iniciar aplicaciones gráficas directamente desde la línea de comandos en lugar de buscar en los menús.
- Aunque las herramientas gráficas pueden variar entre las distribuciones de Linux, la interfaz de línea de comandos no lo hace.

## Uso de un terminal de texto en el escritorio gráfico

Un emulador de terminal emula (simula) un terminal independiente dentro de una ventana del escritorio. Con esto, queremos decir que se comporta esencialmente como si estuviera iniciando sesión en la máquina en un terminal de texto puro sin interfaz gráfica en ejecución. La mayoría de los programas de emuladores de terminal admiten varias sesiones de terminal al abrir pestañas o ventanas adicionales.

De forma predeterminada, en los entornos de escritorio de GNOME, la aplicación de gnome-terminal (terminal de gnome) se utiliza para emular un terminal de modo texto en una ventana. Otros programas de terminal disponibles incluyen:

- xterm
- konsole (predeterminado en KDE)
- terminator

## Algunas utilidades básicas

Hay algunas utilidades básicas de línea de comandos que se utilizan constantemente, y sería imposible avanzar en el curso sin utilizar algunas de ellas de forma sencilla antes de que las discutamos con más detalle. Una breve lista tiene que incluir:

- **cat**: se utiliza para escribir un archivo (o combinar archivos).
- **head**: se utiliza para mostrar las primeras líneas de un archivo.
- **tail**: se utiliza para mostrar las últimas líneas de un archivo.
- **man**: se utiliza para ver la documentación.

Ten en cuenta el uso del símbolo de tubería (|) que sirve para que un programa tome como entrada la salida de otro.

## La línea de comandos

La mayoría de las líneas de entrada introducidas en la línea de comandos del shell tienen tres elementos básicos:

- Comando
- Opciones
- Argumentos

El comando es el nombre del programa que quieres ejecutar. Puede ir seguido de una o más opciones (o modificadores) que modifican lo que puede hacer el comando. Las opciones suelen comenzar con uno o dos guiones, por ejemplo, -p  o  —-print(imprimir), con el fin de diferenciarlos de los argumentos, que representan lo que opera el comando.

Sin embargo, muchos comandos bien no tienen opciones, o no tienen argumentos o ninguno de los dos. Además, otros elementos (como establecer variables de entorno) también pueden aparecer en la línea de comandos al iniciar una tarea.

## Cambio entre la GUI y la línea de comandos

La naturaleza personalizable de Linux permite dejar la interfaz gráfica (temporal o permanentemente) o iniciarla después de que el sistema se haya ejecutado.

La mayoría de las distribuciones Linux ofrecen la opción durante la instalación (o tienen más de una versión del medio de instalación) para elegir entre escritorio (con escritorio gráfico) y servidor (normalmente sin uno).

Los servidores de producción Linux suelen instalarse sin la GUI, e incluso si está instalada, normalmente no se inicia durante el inicio del sistema. Eliminar la interfaz gráfica de un servidor de producción puede ser muy útil para mantener un sistema ajustado, que puede ser más fácil de soportar y de mantener seguro.

