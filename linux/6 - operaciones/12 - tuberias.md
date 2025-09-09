# Tuberías

La filosofía UNIX/Linux es que muchos programas (o comandos) sencillos y cortos cooperen juntos para producir resultados bastante complejos, en lugar de tener un programa complejo con muchas opciones y modos de operación posibles. Para lograrlo, se hace un uso extensivo de tuberías, que canalizan la salida de un comando o programa a otro como entrada.

Para ello, usamos la barra vertical, el símbolo de tubería (|), entre comandos como en:
 
$ comando1 | comando2 | comando3

Lo anterior representa lo que a menudo llamamos canalización y permite a Linux combinar las acciones de varios comandos en uno solo. Esto es extraordinariamente eficiente porque comando2 y comando3 no tienen que esperar a que se completen los comandos de canalización anteriores antes de que puedan comenzar a trabajar con los datos en sus flujos de entrada; con múltiples CPU o sistemas centrales, la potencia informática disponible se utiliza mucho mejor y las cosas se hacen más rápido.

Además, no es necesario guardar la salida en archivos (temporales) entre las etapas de la canalización, lo que ahorra espacio en disco y reduce la lectura y escritura desde el disco, lo que suele ser el cuello de botella al realizar tareas en informática.