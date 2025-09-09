# Descripción de las rutas absolutas y relativas

Existen dos formas de identificar rutas (paths):

## Nombre de ruta absoluto (Absolute pathname)
Un nombre de ruta absoluto comienza por el directorio raíz y sigue el árbol, rama por rama, hasta que llega al directorio o archivo deseado. Las rutas absolutas siempre empiezan por /.

## Nombre de ruta relativo (Relative pathname)
Un nombre de ruta relativo comienza en el directorio de trabajo actual. Las rutas relativas nunca empiezan con /.
Se permite incluir varias barras diagonales (/) entre directorios y archivos, pero el sistema ignora todas las barras diagonales excepto una entre los elementos del nombre de ruta. ////usr//bin es válido, pero el sistema lo interpreta como /usr/bin.

La mayoría de las veces es más conveniente utilizar rutas relativas, que requieren menos escritura si accedemos a directorios que cuelgan del directorio en el que estamos. Por lo general, es conveniente aprovechar los atajos proporcionados por: . (directorio actual), .. (directorio padre) y ~ (tu directorio de inicio).

Por ejemplo, supongamos que estás trabajando actualmente en tu directorio de inicio y quieres desplazarte al directorio absoluto /usr/bin. Las dos formas siguientes te llevarán al mismo directorio desde tu directorio de inicio:

Método de nombre de ruta absoluta
$ cd /usr/bin
Método de nombre de ruta relativa (usamos .. para subir al directorio home general y otros .. para subir desde este al directorio raíz, como puedes comprobar en la imagen que hay más abajo)
$ cd ../../usr/bin
En este caso, el método de nombre de ruta absoluta requiere menos escritura.