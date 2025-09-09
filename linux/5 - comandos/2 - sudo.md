
# sudo

Todas las demostraciones creadas tienen un usuario configurado con capacidades sudo para proporcionar a ese usuario privilegios de administrador cuando sea necesario. sudo permite a los usuarios ejecutar programas utilizando los privilegios de seguridad de otro usuario, generalmente de root (superusuario).

En tus propios sistemas, es posible que tengas que configurar y habilitar sudo para que funcione correctamente. Para ello, debes seguir algunos pasos que no explicaremos con mucho detalle ahora, pero que aprenderás más adelante en este curso. Cuando se ejecuta en Ubuntu y en algunas otras distribuciones recientes, sudo ya está configurado durante la instalación. En otras distribuciones Linux, es probable que tengas que configurar sudo para que funcione correctamente después de la instalación inicial.

A continuación, aprenderás los pasos para configurar y ejecutar sudo en tu sistema.

## Pasos para configurar y ejecutar sudo

Si tu sistema aún no tiene sudo configurado y habilitado, debes seguir los siguientes pasos:

- Tendrás que realizar modificaciones como administrador o superusuario, root (raíz). Mientras que sudo se convertirá en el método preferido para hacerlo, aún no lo tenemos configurado, por lo que usaremos en su lugar **su** (del que hablaremos más adelante en detalle). En el símbolo de línea de comandos, escribe **su** y presiona **Enter**. A continuación, te pedirá la contraseña root, así que introdúcela y presiona **Enter**. Notarás que no se muestra nada; esto es para que otros no puedan ver la contraseña en la pantalla. Lo normal es que cambie el símbolo de la línea de introducción de comandos, que a menudo pasa a terminar con **'#»**. Por ejemplo:

~~~
$ su Contraseña:
#
~~~

- Ahora, necesitas crear un archivo de configuración para permitir que tu cuenta de usuario utilice sudo. Normalmente, este archivo se crea en el directorio **/etc/sudoers.d/**  con el nombre del archivo igual que tu nombre de usuario. Por ejemplo, para esta demostración, supongamos que tu nombre de usuario es **student**. Después de realizar el paso 1, crearías el archivo de configuración para **student** haciendo esto:
~~~
# echo "student ALL=(ALL) ALL" > /etc/sudoers.d/student
~~~
- Por último, algunas distribuciones de Linux se quejarán si no cambias también los permisos del archivo haciendo lo siguiente:
~~~
# chmod 440 /etc/sudoers.d/student
~~~
Eso debería ser todo, **sudo** debería estar configurado correctamente. Cuando uses **sudo**, de forma predeterminada, se te pedirá que proporciones una contraseña (tu propia contraseña de usuario) al menos la primera vez que lo hagas dentro de un intervalo de tiempo especificado. Es posible (aunque muy inseguro) configurar **sudo** para no requerir una contraseña o cambiar el período de tiempo en el que no es necesario repetir la contraseña con cada comando **sudo**.


