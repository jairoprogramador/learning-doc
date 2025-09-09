# Búsqueda de archivos

Poder encontrar rápidamente los archivos que buscas te ahorrará tiempo y mejorará la productividad. Puedes buscar archivos tanto en el espacio del directorio principal como en cualquier otro directorio o ubicación del sistema.

Las principales herramientas para hacerlo son las utilidades locate y find. También mostraremos cómo utilizar comodines en bash para especificar cualquier archivo que coincida con una solicitud generalizada determinada.

## Locate

La utilidad locate realiza una búsqueda aprovechando una base de datos construida previamente de archivos y directorios del sistema, encontrando todas las entradas que contengan una cadena de caracteres especificada. A veces, esto puede dar lugar a una lista muy larga.

Para obtener una lista más corta (y posiblemente más relevante), podemos utilizar el programa grep como filtro. grep imprimirá solo las líneas que contienen una o más cadenas especificadas, como en:

$ locate zip | grep bin

que enumerará todos los archivos y directorios con ambos, zip y bin, en su nombre. Vamos a cubrir grep con mucho más detalle más adelante. Observa el uso de | para usar los dos comandos juntos, canalizando la salida de uno al otro.

locate utiliza una base de datos creada por una utilidad relacionada, updatedb. La mayoría de los sistemas Linux lo ejecutan automáticamente una vez al día. Sin embargo, puedes actualizarlo en cualquier momento simplemente ejecutando updatedb desde la línea de comandos como usuario raíz (root).

## find

find(encontrar) es un programa extremadamente útil y de uso frecuente en la vida cotidiana de un administrador de sistemas Linux. Recorre recursivamente el árbol del sistema de archivos desde cualquier directorio (o conjunto de directorios) en particular y localiza los archivos que coinciden con las condiciones especificadas. El nombre de ruta predeterminado es siempre el directorio de trabajo actual.

Por ejemplo, los administradores a veces analizan en busca de archivos de log potencialmente grandes (con información de diagnóstico después de que un programa falla) que tengan más de varias semanas de antigüedad para eliminarlos.

También es común eliminar archivos de archivos no esenciales u obsoletos en /tmp (y otros directorios volátiles, como los que contienen archivos almacenados en caché) a los que no se ha accedido recientemente. Muchas distribuciones de Linux utilizan scripts de shell que se ejecutan periódicamente (a través de cron por lo general) para realizar tal limpieza.

- sudo find /var/log -name "*log"

### Uso de find

Cuando no se dan argumentos, find (encontrar) enumera todos los archivos del directorio actual y todos sus subdirectorios. Las opciones que se usan comúnmente para acortar la lista incluyen: -name(nombre) (solo enumera los archivos con un patrón determinado en su nombre), -iname (como el anterior pero sin distinguir entre mayúsculas y minúsculas), y -type(tipo) (que restringirá los resultados a archivos de un determinado tipo especificado, como d para directorio , l para un enlace simbólico, o f para un archivo normal, etc.).

Búsqueda de archivos y directorios denominados gcc:

$ find /usr -name gcc

Búsqueda solo de directorios denominados gcc:

$ find /usr -type d -name gcc
$ find /usr -type d -maxdepth 1
este ultimo no muestra los subdirecctorios 

Búsqueda solo de archivos normales denominados gcc:

$ find /usr -type f -name gcc

### Uso de opciones de búsqueda avanzadas

Otro buen uso de  find es ser capaz de ejecutar comandos en los archivos que coincidan con unos criterios de búsqueda. La opción -exec se utiliza para este fin.

Para buscar y eliminar todos los archivos que terminan con .swp:

$ find -name "*.swp" -exec rm {} ';'

El {} (llaves squiggly) es un marcador de posición que se rellenará con todos los nombres de archivo resultantes de la expresión find, y el comando anterior se ejecutará individualmente en cada uno de ellos.

Ten en cuenta que tienes que finalizar el comando con ';' (incluidas las comillas simples) o"\;". Ambas formas valen.

También se puede utilizar la opción -ok, que se comporta igual que -exec, excepto que find te pedirá permiso antes de ejecutar el comando. Esto hace que sea una buena forma de probar los resultados antes de ejecutar ciegamente cualquier comando potencialmente peligroso.


### Búsqueda de archivos según la hora y el tamaño

A veces necesitas buscar archivos según sus atributos, como cuándo se crearon, se usaron por última vez, etc., o según su tamaño. Es fácil realizar esas búsquedas.

Para buscar archivos según el tiempo:

$ find / -ctime 3

Aquí, -ctime se refiere a cuándo los metadatos del inodo (es decir, la propiedad del archivo, permisos, etc.) han cambiado por última vez; a menudo, pero no necesariamente, cuando se creó el archivo por primera vez. También puedes buscar por el tiempo accedido por última vez/última lectura (-atime) o modificado/escrito por última vez (-mtime) . El número es el número de días y se puede expresar como un número (n) que significa exactamente ese valor, +n, lo que significa mayor que ese número, o -n, lo que significa menos que ese número. Existen opciones similares para tiempos en minutos (como en -cmin, -amin, y -mmin).

Para buscar archivos según los tamaños:

$ find / -size 0

Tenga en cuenta que el tamaño está en bloques de 512 bytes, de forma predeterminada; también puedes especificar bytes (c), kilobytes (k), megabytes (M), gigabytes (G), etc. Al igual que con los números de tiempo anteriores, los tamaños de los archivos también pueden ser números exactos (n), +n o -n. Para obtener más información, consulte la página man de find.

Por ejemplo, para buscar archivos de más de 10 MB de tamaño y ejecutar un comando sobre esos archivos:

$ find / -size +10M -exec command {} ';'
