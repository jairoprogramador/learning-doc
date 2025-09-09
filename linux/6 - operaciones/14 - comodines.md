# Comodines y nombres de archivo coincidentes

Puedes buscar un nombre de archivo que contenga caracteres específicos mediante comodines.

comodín	Resultado
? 	    Coincide con cualquier carácter individual
*	    Coincide con cualquier cadena de caracteres
[set]	Coincide con cualquier carácter del conjunto de caracteres, por ejemplo [adf] coincidirá con cualquier ocurrencia de a, d, o f
[!set]  Coincide con cualquier carácter que no esté en el conjunto de caracteres

Para buscar archivos mediante el comodin ? , sustituye cada carácter desconocido por ?. Por ejemplo, si sabes que solo las dos primeras letras son 'ba' de un nombre de archivo de tres letras con una extensión de .out, escribe ls ba?.out.

Para buscar archivos mediante el comodín *, sustituye la cadena desconocida por *. Por ejemplo, si solo recuerdas que la extensión era .out, escribe ls *.out.

Otro ejemplo:

- du -sh a*
- du -sh a*log*
- du -ah a[p-z]*
