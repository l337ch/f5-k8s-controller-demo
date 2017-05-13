# F5 Kubernetes BIG-IP Controller Demo


## Prerequisites
To use this demo you will need the following
* kubectl
* A running Kubernetes cluster
* A working F5 BIG-IP LTM with administrative access to a named partition

## Running the demo

Create a Kubernetes secrets conataining the BIG-IP username, password, and URL using `kubectl`.
```
kubectl create secret generic bigip-login --namespace kube-system --from-literal=username=BIG-IP_USERNAME--from-literal=password=PASSWORD --from-literal=url=BIG-IP_URL
```
