# Sistemas de gestión de paquetes en Linux

Las partes principales de una distribución Linux y la mayor parte de su software adicional se instalan a través de un Sistema de gestión de paquetes (Package Management System). Cada paquete contiene los archivos y otras instrucciones necesarias para que un componente de software funcione bien y coopere con los demás componentes que componen todo el sistema. Los paquetes pueden depender unos de otros. Por ejemplo, un paquete para una aplicación basada en web escrito en PHP puede depender del paquete PHP .

Existen dos familias generales de gestores de paquetes: los basados en Debian y aquellos que utilizan RPM como gestor de paquetes de bajo nivel. Los dos sistemas son incompatibles, pero en términos generales, proporcionan las mismas características y satisfacen las mismas necesidades. Existen otros sistemas utilizados por distribuciones Linux más especializadas.

En esta sección aprenderás a instalar, quitar o buscar paquetes desde la línea de comandos mediante estos dos sistemas de administración de paquetes.

## Gestores de paquetes: dos niveles

Los sistemas de gestión de paquetes funcionan en dos niveles distintos: una herramienta de bajo nivel (como dpkg o rpm) se ocupa de los detalles del desempaquetado de paquetes individuales, la ejecución de scripts y la instalación correcta del software y una herramienta de alto nivel (como apt-get, dnf, yum, o zypper) que funciona con grupos de paquetes, descarga paquetes del proveedor y averigua las dependencias.

La mayoría de las veces los usuarios necesitan trabajar solo con la herramienta de alto nivel, que se encargará de llamar a la herramienta de bajo nivel según sea necesario. La resolución de dependencias es una característica particularmente importante de la herramienta de alto nivel, ya que gestiona los detalles de la búsqueda e instalación de cada dependencia. Sin embargo, ten cuidado, ya que la instalación de un solo paquete podría resultar en la instalación de muchas docenas o incluso cientos de paquetes dependientes.

## Trabajar con diferentes sistemas de gestión de paquetes

La Herramienta de Empaquetado avanzado (Advanced Packaging Tool) apt es el sistema de gestión de paquetes subyacente que administra el software en sistemas basados en Debian. Si bien forma el backend para los gestores de paquetes gráficos, como Ubuntu Software Center y synaptic, su interfaz de usuario nativa se encuentra en la línea de comandos, con programas que incluyen apt (o apt-get) y apt-cache.

dnf es la utilidad de administración de paquetes de línea de comandos de código abierto para los sistemas Linux compatibles con RPM que pertenecen a la familia Red Hat. dnf tiene interfaces de usuario gráficas y de línea de comandos. Fedora y RHEL 8 reemplazaron la utilidad yum más antigua con dnf, eliminando así una gran cantidad de temas históricos e introduciendo muchas capacidades nuevas e interesantes. dnf es prácticamente compatible con yum para los comandos cotidianos.

zypper es el sistema de administración de paquetes para la familia SUSE/openSUSE y también se basa en RPM. zypper también te permite administrar repositorios desde la línea de comandos. zypper es bastante sencillo de usar y se asemeja  mucho a dnf/yum .

Para conocer los comandos básicos de empaquetado, echa un vistazo a estos comandos básicos de empaquetado:

Operación                               RPM                             deb

Instalar paquete                        rpm -i foo.rpm                  dpkg --install foo.deb
Instalar paquete con dependencias       dnf install foo                 apt-get install foo
Eliminar paquete                        rpm -e foo.rpm                  dpkg --remove foo.deb
Eliminar paquete con dependencias       dnf remove foo                  apt-get autoremove foo
Actualizar paquete                      rpm -U foo.rpm                  dpkg --install foo.deb
Actuallizar paquete con dependencias    dnf update foo	                apt-get install foo
Actualizar todo el sistema              dnf update                      apt-get dist-upgrade
Mostrar todos los paquetes instalados   rpm -qa o dnf list installed    dpkg --list
Obtener información sobre el paquete    rpm -qil foo                    dpkg --listfiles foo
Mostrar paquetes denominados foo        dnf list "foo"                  apt-cache search foo
Mostrar todos los paquetes disponibles  dnf list                        apt-cache dumpavail foo
¿De qué paquete es parte file?          rpm -qf file                    dpkg -—search file

## ejemplos dpkg:

- dpkg --list | less
- dpkg --list | grep bzip2
- dpkg --listfiles bzip2 | less
- sudo dpkg --remove bzip2

## ejemplo rpm:

- rpm -qa | grep bzip2
- rpm -qil bzip2 | less
- ls -lF $(rpm -ql bzip2) | less
- sudo rpm -e --test bzip2
- rpm -q --whatprovides bzip2
- rpm -q --whatrequires bzip2

## ejemplos dnf:

- sudo dnf list *bzip2*
- sudo dnf install lbzip2-utils
- sudo dnf remove lbzip2-utils

## ejemplos zypper

- zypper search gnuplot
- sudo zypper install gnuplot-doc
- rpm -qi gnuplot-doc
- sudo zypper remove gnuplot

## ejemplos apt

- apt-cache search wget2
- sudo apt-get install wget2-dev
- sudo apt-get remove wget2