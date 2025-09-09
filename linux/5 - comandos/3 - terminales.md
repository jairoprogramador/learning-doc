# Terminales virtuales

Los Terminales virtuales (Virtual Terminals VT) son sesiones de consola que utilizan toda la pantalla y el teclado fuera de un entorno gráfico. Estos terminales se consideran "virtuales" porque, aunque pueden haber varios terminales activos, solo queda visible un terminal a la vez. Un VT no es lo mismo que una ventana de terminal de línea de comandos; puedes tener muchas de ellas visibles a la vez en un escritorio gráfico.

Se reserva un terminal virtual (normalmente el número uno o siete) para el entorno gráfico y los inicios de sesión de texto están habilitados en los VT no utilizados. Ubuntu usa VT 7, pero CentOS/RHEL y openSUSE utilizan VT 1 para la pantalla gráfica.

Un ejemplo de situación en la que el uso de VT resulta útil es cuando tienes problemas con el escritorio gráfico. En esta situación, puede cambiar a uno de los VT de texto y solucionar los problemas.

Para cambiar entre VT, pulsa CTRL-ALT-tecla función para el VT. Por ejemplo, presione CTRL-ALT-F6 para VT 6. En realidad, solo tienes que presionar el ALT-F6 si estás en un VT y quieres cambiar a otro VT.