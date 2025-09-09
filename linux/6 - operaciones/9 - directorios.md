# mkdir y rmdir

mkdir se utiliza para crear un directorio:

mkdir sampdir 
Crea un directorio de ejemplo denominado sampdir en el directorio actual. Tambien se puede crear varios directorios simplemente agregando sus nombre: **mkdir name1 name2 name3**

mkdir /usr/sampdir 
Crea un directorio de ejemplo llamado sampdir bajo /usr(usuario).
La eliminación de un directorio se realiza con rmdir. El directorio debe estar vacío o el comando fallará. Para eliminar un directorio y todo su contenido tienes que hacerlo rm -rf.

rmdir funciona solo en directorios vacíos; de lo contrario, devuelve un error.

rm —rf es una forma rápida y fácil de eliminar recursivamente un árbol del sistema de archivos completo, pero es extremadamente peligroso y debe utilizarse con el máximo cuidado, especialmente cuando se usa con el usuario root (recordemos que el uso recursivo implica eliminar todos los subdirectorios, hasta el final de un árbol).

- mv	  : Cambiar el nombre de un directorio
- rmdir	  : Eliminar un directorio vacío
- rm -rf  :	Eliminar un directorio con fuerza de forma recursiva