# Modificación del símbolo de línea de comandos

La variable PS1 es la cadena de caracteres que se muestra como símbolo en la línea de comandos. La mayoría de distribuciones ponen PS1 a un valor predeterminado conocido, que es adecuado en la mayoría de los casos. Sin embargo, es posible que los usuarios deseen que se muestre información personalizada en la línea de comandos. Por ejemplo, algunos administradores del sistema requieren que el usuario y el nombre del sistema host se muestren en la línea de comandos como en:

student@c8 $

Esto podría resultar útil si trabajas en varios roles y quieres que siempre te recuerden quién eres y en qué máquina estás. El mensaje anterior podría implementarse configurando el PS1 variable a: \u@\h \$.

Por ejemplo:

$ echo $PS1
\$
$ PS1= "\u@\h \$»
student@c8 $ echo $PS1
\u@\h \$
student @c8 $

Por convención, la mayoría de los sistemas se configuran para que el usuario root tenga un signo de almohadilla (#) para que se distinga claramente cuando estamos trabajando con privilegios de root.