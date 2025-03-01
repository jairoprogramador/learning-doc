# ¿Que es un deployment?

Un **Deployment** es una capa superior que gestiona **ReplicaSets** y proporciona una forma declarativa de implementar y actualizar las instancias de una aplicación. Es la forma más común de gestionar aplicaciones en Kubernetes.

# ¿Que es un rollout?

Es el proceso de implementación o actualización controlada de un Deployment, DaemonSet o StatefulSet. Permite gestionar la transición de una versión antigua a una nueva de una aplicación sin causar interrupciones en el servicio y permitiendo reversión en caso de fallos.

# ¿Que es un port-forward?

Es un comando que permite redirigir el tráfico desde tu máquina local a un Pod, Service, o Deployment dentro del clúster. Esto es útil cuando quieres acceder a una aplicación en Kubernetes sin exponerla mediante un Service con LoadBalancer o NodePort.
El comando crea un túnel temporal entre un puerto local y un puerto en un Pod o Service dentro del clúster, permitiendo que accedas a la aplicación como si estuviera corriendo en tu propia máquina.