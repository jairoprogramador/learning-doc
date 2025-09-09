# Enlaces

La utilidad ln se utiliza para crear enlaces duros (hard) y (con la opción -s) enlaces suaves (soft), también conocidos como enlaces simbólicos o symlinks. Estos dos tipos de enlaces son muy útiles en los sistemas operativos basados en UNIX.

## Enlaces duros

Supongamos que file1 existe. Un enlace duro, llamado file2, se crea con el comando:

$ ln file1 file2

Ahora parecen que hay dos archivos. Sin embargo, una inspección más detallada de la lista de archivos muestra que esto no es del todo cierto.

$ ls -li file1 file2

La opción -i para ls imprime en la primera columna el número de inodo, que es un número único para cada objeto de archivo. Este campo es el mismo para ambos archivos; lo que realmente pasa es que es solo hay un archivo, pero tiene más de un nombre asociado a él, como se indica en el 2 que aparece en la salida ls. Por lo tanto, ya había otro objeto vinculado a file 1 antes de que ejecutara el comando.

Los enlaces duros son muy útiles y ahorran espacio, pero hay que tener cuidado con su uso, pues a veces tienen implicaciones sutiles. Por ejemplo, si eliminas cualquiera de las dos, file 1 o file 2 en el ejemplo, el objeto inode y el nombre de archivo restante permanecerán, lo que podría no ser deseable, ya que podría provocar errores difíciles de detectar más adelante si vuelve a crear un archivo con ese nombre.

Si editas uno de los archivos, lo que suceda dependerá del editor; la mayoría de los editores, incluidos vi y gedit, conservará de forma predeterminada el enlace , pero es posible que la modificación de uno de los nombres rompa el enlace y dé lugar a la creación de dos objetos.

## Enlaces suaves (simbolicos)

Los vínculos suaves -soft- (o simbólicos) se crean con la opción -s, como en:

$ ln -s file1 file3
$ ls -li file1 file3

Fíjate en la imagen en que file 3 ya no aparece como un archivo normal y apunta claramente a file 1 y, además, tiene un número de inodo diferente.

Los enlaces simbólicos no ocupan espacio adicional en el sistema de archivos (a menos que sus nombres sean muy largos). Son extremadamente convenientes, ya que se pueden modificar fácilmente para apuntar a diferentes lugares. Una forma sencilla de crear un atajo desde tu directorio home  a nombres de ruta largos consiste en crear un enlace simbólico.

A diferencia de los enlaces duros, los enlaces blandos pueden apuntar a objetos incluso en diferentes sistemas de archivos, particiones y/o discos y otros medios, que pueden estar disponibles o no actualmente o incluso no existir. En el caso de que el enlace no apunte a un objeto disponible o existente actualmente, obtendrás un enlace colgante.

