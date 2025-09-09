# Las páginas man

Las páginas man son la fuente de documentación de Linux que se utiliza con más frecuencia. Proporcionan documentación detallada sobre muchos programas y utilidades, así como otros temas, incluidos archivos de configuración y API de programación para llamadas al sistema, rutinas de biblioteca y kernel. Están presentes en todas las distribuciones Linux y siempre están al alcance de tu mano.

La infraestructura de las paginas man se introdujo por primera vez en las primeras versiones de UNIX, a principios de la década de 1970. El nombre man es solo una abreviatura de manual.

 Escribiendo man con un nombre de tema como argumento recuperas la información almacenada en las páginas man sobre ese tema.

Las páginas man se convierten a menudo a otros formatos, como documentos PDF y páginas web. Para obtener más información, échale un vistazo a Páginas man de Linux en línea. Muchas páginas web tienen una interfaz gráfica para elementos de ayuda, que pueden incluir páginas de manual.

Otras fuentes de documentación incluyen libros publicados y muchos sitios de Internet.

## man

El programa man busca, da formato y muestra la información contenida en el sistema de páginas man. Dado que muchos temas tienen una gran cantidad de información relevante, la salida se canalizará a través de un programa paginador (como less) para que se vea una página cada vez. Al mismo tiempo, la información está formateada para una buena visualización.

Un tema determinado puede tener varias páginas asociadas y hay un orden predeterminado que determina cuál se muestra cuando no se especifica ninguna opción o número de sección. Para listar todas las páginas del tema, utiliza opción -f. Para listar todas las páginas que discuten un tema específico (incluso si el asunto especificado no está presente en el nombre), utiliza la opción —k.

- man —f  genera el mismo resultado que escribir   whatis.
- man —k  genera el mismo resultado que escribir  apropos.

El orden predeterminado se especifica en /etc/man_db.conf  y está aproximadamente (pero no exactamente) en orden numérico ascendente por sección.

### Capítulos en los manuales

Las páginas man se dividen en capítulos numerados del 1 al 9. En algunos casos, se añade una letra al número de capítulo para identificar un tema específico. Por ejemplo, muchas páginas que describen parte de la API de X Window se encuentran en el capítulo 3X.

El número de capítulo se puede utilizar para obligar a man a mostrar la página de un capítulo concreto. Es común tener varias páginas en varios capítulos con el mismo nombre, especialmente para nombres de funciones de biblioteca o llamadas al sistema.

Con el parametro -a , man mostrará todas las páginas con el nombre especificado en todos los capítulos, una tras otra, como en:

- $ man -a socket