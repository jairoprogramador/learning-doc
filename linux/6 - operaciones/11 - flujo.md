# Flujos de archivos estándar

Cuando se ejecutan comandos, hay tres flujos de archivos estándar (o descriptores) siempre abiertos para su uso de forma predeterminada : entrada estándar (standard in o stdin), salida estándar (standard out stdout) y error estándar (o stderr).

Nombre	 Nombre     simbólico	Valor	Ejemplo
entrada  estándar	stdin	    0	    teclado
salida   estándar	stdout	    1	    terminal
error    estándar	stderr	    2	    archivo de registro

Por lo general, stdin es tu teclado, y stdout y stderr se imprimen en tu terminal. stderr a menudo se redirige a un archivo de registro de errores, mientras que a stdin se le puede redirigir la entrada para que proceda de un archivo o de la salida de un comando anterior a través de una tubería. stdout también se redirige a menudo a un archivo. Como stderr es donde se escriben los mensajes de error, lo normal es que nada salga por ella.

En Linux, todos los archivos abiertos están representados internamente por lo que se denominan descriptores de archivos. En pocas palabras, están representados por números que comienzan en cero. stdin es el descriptor de archivo 0, stdout es el descriptor de archivo 1, y stderr es el descriptor de archivo 2. Normalmente, si se abren otros archivos además de estos tres, que se abren de forma predeterminada, se iniciarán en el descriptor de archivo 3 y aumentarán a partir de ahí.

## Redirección de E/S

A través del intérprete (shell) de comandos, podemos redirigir los tres flujos de archivos estándar para obtener información de un archivo o de otro comando, en lugar de desde nuestro teclado, y podemos escribir los resultados y errores en archivos o utilizarlos para proporcionar la entrada a comandos posteriores.

Por ejemplo, si tenemos un programa llamado do_something (haz algo) que lee desde stdin y escribe a stdout y stderr, podemos cambiar su fuente de entrada utilizando el signo menor que (<) seguido del nombre del archivo que va a enviar los datos de entrada en lugar del teclado:

$ do_something < archivo_entrada

Si deseas enviar la salida a un archivo, utiliza el signo mayor que (>) como en:

$ do_something > archivo_salida

Como stderr no es lo mismo que stdout, los mensajes de error seguirán apareciendo en la ventana de la terminal en el ejemplo anterior.

Si quieres redirigir stderr a un archivo separado, usa el numero de descriptor numero 2 de  stderr, el signo mayor que (>), seguido del nombre del archivo en el que quieras guardar todo lo que escribe el comando en ejecución en stderr:

$ do_something 2> archivo_error

NOTA: Según la misma lógica, do_something 1> archivo_salida  es lo mismo que do_something > archivo_salida


Con una notación abreviada especial se puede enviar cualquier cosa escrita en el descriptor de archivo 2 (stderr) al mismo sitio que lo enviado al descriptor de archivo 1 (stdout): 2>&1.

$ do_something > archivo_salida 2>&1

bash permite una sintaxis más sencilla para lo anterior:

$ do_something >& archivo_salida
