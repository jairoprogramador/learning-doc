## 💡 Forma declarativa

* **Crear un Service tipo NodePort**

```
kubectl apply -f deployment-nodeport.yaml

```

* **Crear un Service tipo ClusterIP**

```
kubectl apply -f deployment-clusterip.yaml
```

* **Crear un Service tipo LoadBalancer**

```
kubectl apply -f deployment-loadbalancer.yaml
```

* **Crear un Service tipo ExternalName**

```
kubectl apply -f externalname.yaml
```