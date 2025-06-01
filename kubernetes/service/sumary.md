# ¿Que es un Service?

Es una abstracción que le ayuda a exponer grupos de pods en una red. Cada objeto **Service** define un conjunto lógico de puntos finales (normalmente, estos puntos finales son pods) junto con una política sobre cómo hacer que esos pods. Trabaja con los protocolos TCP(default), SCTP y UDP

## Tipos de Service

* **ClusterIP (default)**
Expone el **Service** en una dirección IP interna del clúster. Si elige este valor, **solo se podrá acceder al servicio desde dentro del clúster**. Este es el valor predeterminado que se utiliza si no especifica explícitamente un `type`. Un caso de uso tipico es la comunicación interna entre pods. Puede exponer el servicio a Internet público mediante un Ingress o un Gateway

* **NodePort**
Expone el **Service** en la IP de cada nodo en un puerto estático (el `NodePort`). Para que el puerto del nodo esté disponible, Kubernetes configura una dirección IP del clúster, igual que si hubiera solicitado un servicio de `type: ClusterIP`. Se puede acceder al **Service** de manera **externa o desde cualquier nodo del clúster** sin la necesidad de un LoadBalancer.

* **LoadBalancer**
Expone el **Service** de forma externa mediante un balanceador de carga externo. Kubernetes no ofrece directamente un componente de balanceo de carga; debes proporcionar uno o puedes integrar tu clúster de Kubernetes con un proveedor de nube.

* **ExternalName:** 
Asigna el **Service** al contenido del campo `externalName` (por ejemplo, al nombre de host `api.foo.bar.example`). La asignación configura el servidor DNS de su clúster para que devuelva un registro `CNAME` con ese valor de nombre de host externo. No se configura ningún tipo de proxy. Dicho de otro modo, permite redirigir las solicitudes a un **nombre de dominio externo**, en lugar de a un conjunto de pods dentro del clúster, actúa como un **alias DNS** para un servicio externo. Un **Service ExternalName no crea una IP ni abre puertos**, simplemente devuelve el nombre de dominio especificado cuando se consulta desde dentro del clúster. Es útil cuando queremos referenciar servicios externos mediante un nombre DNS en Kubernetes sin necesidad de exponer puertos ni balancear tráfico. Es una solución simple para mejorar la gestión de dependencias externas.

