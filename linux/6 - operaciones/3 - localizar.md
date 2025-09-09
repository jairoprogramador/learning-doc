# Localización de aplicaciones

Según las características específicas de la política de tu distribución en particular, los programas y paquetes de software se pueden instalar en varios directorios. En general, los programas ejecutables y scripts deberían estar en /bin, /usr/bin, /sbin, /usr/sbin  o en algún lugar bajo /opt. También pueden estar en /usr/local/bin y /usr/local/sbin, o en un directorio del espacio de cuenta de un usuario, como /home/estudiante/bin.

Una forma de localizar los programas es emplear la utilidad "which". Por ejemplo, para averiguar exactamente dónde reside el programa diff en el sistema de archivos:

$ which diff
/usr/bin/diff

Si which no encuentra el programa, whereis es una buena alternativa porque busca paquetes en una gama más amplia de directorios de sistema:

$ whereis diff
diff: /usr/bin/diff /usr/share/man/man1/diff.1.gz /usr/share/man/man1p/diff.1p.gz

Localiza también los ficheros fuentes y man empaquetados con el programa.