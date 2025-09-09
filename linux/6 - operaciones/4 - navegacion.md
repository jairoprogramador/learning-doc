# Acceso a directorios

La primera vez que inicias sesión en un sistema o abres un terminal, el directorio predeterminado debería ser tu directorio personal. Puedes imprimir su ruta exacta escribiendo echo $HOME. Muchas distribuciones de Linux abren terminales gráficos nuevos en $HOME/desktop. Los siguientes comandos son útiles para la navegación de directorios:

- pwd	    : Muestra el directorio de trabajo actual
- cd ~ o cd	: Cambiar a tu directorio personal (el nombre del método abreviado es ~ (tilde))
- cd ..	    : Cambio al directorio padre (..)
- cd -	    : Cambio al directorio anterior (- (menos))
- pushd [directorio] : Cambia al directorio especificado y simultaneamente guarda directorio actual en una pila de directorios
- popd      : Elimina el directorio superior de la pila y cambia a ese directorio
- dirs -v   : Muestra la pila numerada
- dirs -c   : Limpia la pila

