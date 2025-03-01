## 💻 Forma imperativa (CLI)

* **Ver estado del rolluot**

```
kubectl rollout status deployment <nombre-deployment>
```

* **Deshacer un rollout**

```
kubectl rollout undo deployment <nombre-deployment>
```

* **Ver el historial de rollouts:**

```
kubectl rollout history deployment <nombre-deployment>
```