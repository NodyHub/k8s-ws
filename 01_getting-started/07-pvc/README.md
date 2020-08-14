# Persistent Volumes

**DANGER!** read. [Container Breakouts – Part 1: Access to root directory of the Host](https://blog.nody.cc/posts/container-breakouts-part1/)

## Create the pod

```
kubectl create -f yaml/pvc-pod.pod.yaml
```

## See that the pod is not started

```
kubectl get pod pvc-pod
```

## Create Persistent Volume Claim (necessary for pod)

```
kubectl create -f yaml/pvc-test.pvc.yaml
```

## See that the pod is still not started and the volume is pending

```
kubectl get pod pvc-pod
kubectl get pvc pvc-test
```

## Create Persistent Volume, so that the PVC can allocate it

```
kubectl create -f yaml/pv-test.pv.yaml
```

## Check The PVC that the PV is allocated

```
kubectl get pvc
kubectl get pv
```

## See that the volume is mounted (empty)

```
kubectl exec -it pvc-pod -- ls -l /data
```

## Create a file in the volume

```
kubectl exec -it pvc-pod -- echo "Test" > /data/hello-from-the-pod.txt
```

## Delete pod & Create him again

```
kubectl delete pod pvc-pod
kubectl create -f yaml/pvc-pod.pod.yaml
```

## See that the file is still there

```
kubectl exec -it pvc-pod -- ls -l /data
```

