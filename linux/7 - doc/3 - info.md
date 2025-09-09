# El sistema de información GNU

La siguiente fuente de documentación de Linux es el sistema de Información GNU .

Este es el formato de documentación estándar del proyecto GNU, al que prefiere como alternativa a man. El sistema de información está  presentado en un formato libre y admite subsecciones vinculadas.

Funcionalmente, info se parece al man en muchos sentidos. Sin embargo, los temas se conectan mediante enlaces (aunque su diseño es anterior a la World Wide Web). La información se puede ver a través de una interfaz de línea de comandos, una utilidad de ayuda gráfica, imprimida o visualizada en línea.

## Uso de la información de la línea de comandos

Escribiendo info sin argumentos en una ventana de terminal se muestra un índice de temas disponibles. Puedes navegar por la lista de temas utilizando las teclas de movimiento regulares: con las teclas arriba, abajo, izquierda y derecha, pagina arriba y página abajo.

Puede ver la ayuda de un tema concreto escribiendo info <nombre del tema>.  A continuación, el sistema busca el tema en todos los archivos info disponibles.

Algunas teclas útiles son: q para salir, h para obtener ayuda, y Enter para seleccionar un elemento de menú.

## info Estructura de página

El tema que ves en una página de información se denomina nodo. En la tabla se enumeran las pulsaciones de teclas básicas para moverse entre nodos.

Los nodos son esencialmente secciones y subsecciones de la documentación. Puedes moverte entre nodos o ver cada nodo secuencialmente. Cada nodo puede contener menús y subtemas o elementos vinculados.

Los elementos funcionan como enlaces del navegador y se identifican mediante un asterisco (*) al principio del nombre del artículo. Los elementos con nombre (fuera de un menú) se identifican con dos puntos (::) al final del nombre del artículo. Los elementos pueden hacer referencia a otros nodos del archivo o a otros archivos.

Clave	Función
n	    Ir al siguiente nodo
p	    Ir al nodo anterior
u	    Mover un nodo hacia arriba en el índice