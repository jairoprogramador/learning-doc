# Trabajo con archivos

Linux proporciona muchos comandos que te ayudan a ver el contenido de un archivo, crear un nuevo archivo o un archivo vacío, cambiar la marca de hora de un archivo y mover, quitar y cambiar el nombre de un archivo o directorio. Estos comandos te ayudan a administrar tus datos y archivos y a garantizar que los datos correctos estén disponibles en la ubicación correcta.

## Visualizacion
Puede utilizar las siguientes utilidades de línea de comandos para ver los archivos:

- cat	Se utiliza para ver archivos que no son muy largos; no proporciona ningún desplazamiento hacia atrás. Con la opcion **-n**  (**cat -n file**) te muestra el numero de linea.
- tac	Se utiliza para mirar un archivo hacia atrás, empezando por la última línea. Lo contrario de cat.
- less	Se utiliza para ver archivos más grandes porque es un programa de paginación. Hace una pausa en cada pantalla llena de texto, proporciona funciones de desplazamiento hacia atrás y le permite buscar y navegar por el archivo. Con la barra espaciadora puedo ir de pagina en pagina. Tambien tiene la opcion **-N** (**less -N file**) para mostrar el numero de linea.

NOTA: Usa / para buscar un patrón en la dirección hacia adelante y ? para un patrón en la dirección hacia atrás. Todavía se utiliza un programa más antiguo llamado more, pero tiene menos capacidades: «menos es más».
- tail	Se utiliza para imprimir las últimas 10 líneas de un archivo de forma predeterminada. Puede cambiar el número de líneas haciendo -n 15 o simplemente -15 si querías mirar las últimas 15 líneas en lugar de las predeterminadas.
- head	Lo opuesto a tail; de forma predeterminada, imprime las 10 primeras líneas de un archivo, si queremos ver otro numero de lineas, es similar a **tail**

## Mover, cambiar el nombre o eliminar un archivo

Tenga en cuenta que mv tiene doble utilidad, en el sentido de que puede:

- Simplemente cambiar el nombre de un archivo
- Mover un archivo a otra ubicación y, posiblemente, cambiar su nombre al mismo tiempo.

Si no estás seguro de eliminar los archivos que coinciden con un patrón suministrado, siempre es bueno ejecutar rm interactivamente (rm —i) para preguntar antes de cada retirada.

- mv	: Cambiar el nombre de un archivo; **mv file fileNewName**
- rm	: Eliminar un archivo
- rm —f	: Eliminar un archivo a la fuerza
- rm —i	: Eliminar un archivo de forma interactiva con confirmación


# Touch

touch se utiliza a menudo para configurar o actualizar el acceso, cambiar y modificar las horas de los archivos. De forma predeterminada, restablece la marca de hora de un archivo para que coincida con la hora actual.

Sin embargo, también puede crear un archivo vacío utilizando touch:

$ touch <filename>

Esto se hace normalmente para crear un archivo vacío como marcador de posición para un propósito posterior.

touch proporciona varias opciones útiles. Por ejemplo, la opcion -t permite establecer la fecha y la fecha y hora del archivo en un valor específico, como en:

$ touch -t 12091600 myfile

Esto establece el myfile fecha y hora del archivo hasta las 16 p.m., 9 de diciembre (12 09 1600).

# echo

Otra forma de crear un archivo es con **echo > file**
