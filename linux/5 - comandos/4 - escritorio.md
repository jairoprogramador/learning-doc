# Desactivación del escritorio gráfico

Las distribuciones de Linux pueden iniciar y detener el escritorio gráfico de varias formas. El método exacto difiere de la distribución y entre las versiones de distribución. Para las distribuciones basadas en sistemas más recientes, el gestor de pantallas se ejecuta como servicio, por lo que puedes detener el escritorio de la GUI con la utilidad systemctl y en la mayoría de las distribuciones también funcionará con el comando telinit, como en:

$ sudo systemctl stop gdm (o sudo telinit 3)

y reiniciarlo (después de iniciar sesión en la consola) con:

$ sudo systemctl start gdm (o sudo telinit 5)

En las versiones de Ubuntu anteriores a 18.04 LTS, sustituye lightdm por gdm.

Métodos para desactivar la interfaz gráfica de usuario GUI:
     student:/tmp> sudo systemctl stop gdm
     student:/tmp> sudo systemctl stop lightdm
     student:/tmp> sudo telinit 3
      
Métodos para volver a activar la interfaz gráfica de usuario GUI:
     student:/tmp> sudo systemctl start gdm
     student:/tmp> sudo systemctl start lightdm
     student:/tmp> sudo telinit 5