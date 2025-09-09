# Reinicio y apagado

El método preferido para apagar o reiniciar el sistema es utilizar el comando **shutdown** (apagado). Esto envía un mensaje de advertencia y, a continuación, impide que otros usuarios inicien sesión. El proceso de init controlará el apagado o el reinicio del sistema. Es importante apagarlo siempre correctamente; si no lo hace, puede provocar daños en el sistema y/o pérdida de datos.

Los comandos **halt** y **poweroff** lanzan **shutdown -h** para detener el sistema; **reboot** ejecuta **shutdown -r** y hace que la máquina se reinicie en lugar de simplemente apagarse. Tanto el reinicio como el apagado desde la línea de comandos requieren acceso de superusuario (root).

Al administrar un sistema multiusuario, tienes la opción de notificar a todos los usuarios antes de apagarlo, como en:

~~~
$ sudo shutdown -h 10:00 "Apagado para mantenimiento programado".
~~~

NOTA: En las distribuciones recientes de Linux basadas en Wayland, estos mensajes de difusión no aparecen en las sesiones de emulación de terminales que se ejecutan en el escritorio; solo aparecen en las pantallas de la consola VT.