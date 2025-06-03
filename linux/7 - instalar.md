# Instalación de Linux

## Planificación

El diseño de la partición debe decidirse en el momento de la instalación; puede ser difícil cambiarlo posteriormente. Si bien los sistemas Linux manejan varias particiones montándolas en puntos específicos del sistema de archivos y siempre se puede modificar el diseño más adelante, siempre es más fácil intentar hacerlo bien desde el principio.
Casi todos los instaladores proporcionan un diseño predeterminado razonable, ya sea con todo el espacio dedicado a archivos normales en una partición grande y una partición de intercambio más pequeña, o bien con particiones separadas para algunas áreas sensibles al espacio, como /home y /var. Es posible que tenga que anular los valores predeterminados y hacer algo diferente si tiene necesidades especiales o si desea utilizar más de un disco.

## Opciones de software

Todas las instalaciones incluyen el software mínimo para ejecutar una distribución Linux.

La mayoría de los instaladores también ofrecen opciones para agregar categorías de software. Aplicaciones comunes (como el navegador web Firefox y la suite ofimática LibreOffice), herramientas para desarrolladores (como el vi y emacs, editores de texto, que exploraremos más adelante en este curso) y otros servicios populares (como las herramientas del servidor web Apache o la base de datos MySQL) suelen incluirse. Además, para cualquier sistema con un escritorio gráfico, el escritorio elegido (como GNOME o KDE) se instala de forma predeterminada.

Todos los instaladores configuran algunas funciones de seguridad iniciales en el nuevo sistema. Un paso básico consiste en configurar la contraseña del superusuario (root) y configurar un usuario inicial. En algunos casos (como Ubuntu), solo se configura un usuario inicial; el inicio de sesión root directo no se configura y el acceso root requiere iniciar sesión primero como usuario normal y luego usar sudo, como describiremos más adelante. Algunas distribuciones también instalarán marcos de seguridad más avanzados, como SELinux o AppArmor. Por ejemplo, todos los sistemas basados en Red Hat, incluidos Fedora y CentOS, siempre usan SELinux de forma predeterminada, y Ubuntu viene con AppArmor en funcionamiento.

## Fuente de la instalación

Al igual que otros sistemas operativos, las distribuciones de Linux se proporcionan en medios extraíbles, como unidades USB, CD o DVD. La mayoría de las distribuciones Linux también admiten arrancar una imagen pequeña y descargar el resto del sistema a través de la red. Estas imágenes pequeñas se pueden utilizar en dispositivos extraíbles o como imágenes de arranque de red, en cuyo caso es posible realizar una instalación sin utilizar ningún medio local.

Muchos instaladores pueden realizar una instalación completamente automática, utilizando un archivo de configuración para especificar las opciones de instalación. Este archivo se denomina archivo Kickstart para sistemas basados en Red Hat, perfil AutoYast para sistemas basados en SUSE y archivo Preseed para sistemas basados en Debian.

Cada distribución proporciona su propia documentación y herramientas para crear y administrar estos archivos.

## El proceso

El proceso de instalación real es bastante similar para todas las distribuciones. Después de arrancar desde el medio de instalación, el instalador se inicia y hace preguntas sobre cómo debe configurarse el sistema. Estas preguntas se omiten si se proporciona un archivo de instalación automática. A continuación, se realiza la instalación.

Por último, el equipo se reinicia en el sistema recién instalado. En algunas distribuciones, se hacen preguntas adicionales después de reiniciar el sistema.

La mayoría de los instaladores tienen la opción de descargar e instalar actualizaciones como parte del proceso de instalación; esto requiere acceso a Internet. De lo contrario, el sistema utiliza su mecanismo de actualización normal para recuperar esas actualizaciones una vez finalizada la instalación.


