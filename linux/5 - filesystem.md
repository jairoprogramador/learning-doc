# Sistema de Archivos

## Introducción

El sistema de archivos en Linux es fundamental para entender cómo el sistema operativo organiza y gestiona la información. No solo almacena archivos, sino que también mantiene un registro detallado de su ubicación, propiedades y relaciones entre ellos.

## Tipos

Linux soporta una amplia variedad de sistemas de archivos, cada uno con sus propias características y casos de uso:

### Tradicionales
- **ext4**: El sistema de archivos más común en Linux, con soporte para journaling y archivos de hasta 1 exabyte
- **XFS**: Optimizado para archivos grandes y alto rendimiento
- **Btrfs**: Sistema de archivos moderno con características avanzadas como snapshots y RAID integrado
- **JFS**: Sistema de archivos de IBM, conocido por su estabilidad
- **NTFS**: Soporte para sistemas de archivos de Windows
- **vfat/exfat**: Para compatibilidad con dispositivos externos

### Especializados
- **Sistemas para almacenamiento flash**: ubifs, jffs2, yaffs
- **Sistemas de base de datos**: Para aplicaciones que requieren acceso rápido a datos estructurados
- **Sistemas con fines especiales**:
  - **procfs**: Proporciona información sobre procesos y estado del kernel
  - **sysfs**: Expone información sobre dispositivos y drivers
  - **tmpfs**: Sistema de archivos en memoria
  - **squashfs**: Sistema de archivos de solo lectura comprimido
  - **debugfs**: Para depuración del kernel
  - **fuse**: Framework para sistemas de archivos en espacio de usuario

## Particiones y Sistemas de Archivos

### Conceptos Fundamentales

Una **partición** es una sección lógica de un disco duro que puede contener un sistema de archivos. Es importante entender que:

- Las particiones pueden ser primarias o extendidas
- Una partición extendida puede contener múltiples particiones lógicas
- El límite tradicional es de 4 particiones primarias por disco
- GPT (GUID Partition Table) permite más particiones y discos más grandes

Un **sistema de archivos** es la estructura que organiza cómo se almacenan y recuperan los datos en una partición. Características importantes:

- Gestión de metadatos (propiedades de archivos)
- Control de acceso
- Journaling (en sistemas modernos)
- Gestión de espacio
- Integridad de datos

## El Estándar de Jerarquía (FHS)

El Filesystem Hierarchy Standard (FHS) es crucial para la interoperabilidad entre distribuciones Linux. Los directorios principales son:

- **/**: Directorio raíz
- **/bin**: Comandos esenciales del sistema
- **/boot**: Archivos de arranque
- **/dev**: Dispositivos
- **/etc**: Configuración del sistema
- **/home**: Directorios de usuarios
- **/lib**: Bibliotecas esenciales
- **/media**: Puntos de montaje para medios removibles
- **/mnt**: Puntos de montaje temporales
- **/opt**: Software adicional
- **/proc**: Información de procesos
- **/root**: Directorio home del superusuario
- **/sbin**: Comandos del sistema
- **/tmp**: Archivos temporales
- **/usr**: Programas y datos de usuario
- **/var**: Datos variables

### Características Importantes

1. **Sensibilidad a mayúsculas/minúsculas**: Linux distingue entre mayúsculas y minúsculas en nombres de archivos
2. **Separador de rutas**: Usa '/' en lugar de '\\' (Windows)
3. **Sin letras de unidad**: Todo se monta bajo el árbol de directorios
4. **Puntos de montaje**: Cualquier directorio puede ser un punto de montaje
5. **Enlaces**: Soporte para enlaces simbólicos y duros

### Montaje de Dispositivos

Los dispositivos extraíbles modernos se montan típicamente en:
- `/run/media/usuario/etiqueta` (sistemas modernos)
- `/media` (sistemas más antiguos)

Por ejemplo, un USB con etiqueta "DATOS" para el usuario "juan" estaría en:
`/run/media/juan/DATOS/`