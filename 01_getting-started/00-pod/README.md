# Container to pod

## List All

```
kubectl get all 
``

## List Namespaces 

```
kubectl get ns
```

## List Pods of current namespace

```
kubectl get pods
```


## Start Pod

```
kubectl run k8s-ws --image nodyd/k8s-ws
```

## List Pods

```
kubectl get pods
```

## Exec into pod

```
kubectl exec -it k8s-ws -- bash
```

## curl localhost

```
curl 127.0.0.1:5000
```

## Delete pod

```
kubectl delete pod k8s-ws
```

## List Pods

```
kubectl get pods
```
