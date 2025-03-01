# ¿Que es un pod?

Es la **unidad mínima de despliegue en Kubernetes** que encapsulan uno o más contenedores. Los contenedores de un pod comparte la misma red, almacenamiento y el mismo ciclo de vida:

- Red: Todos los contenedores dentro de un Pod comparten la misma dirección IP y puerto.
- Almacenamiento: Los contenedores pueden compartir volúmenes montados.
- Ciclo de vida: Los contenedores dentro de un Pod se crean, ejecutan y eliminan juntos.

Kubernetes no gestiona contenedores directamente, sino **pods**.
