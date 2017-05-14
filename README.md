# F5 Kubernetes BIG-IP Controller Demo

## Introduction

This demo uses F5'a bigip-k8s-ctlr 

## Prerequisites
To use this demo you will need the following
* kubectl
* A running Kubernetes cluster
* A working F5 BIG-IP LTM with administrative access to a named partition

## Running the demo

### Step 1
Create a Kubernetes secrets conataining the BIG-IP username, password, and URL using `kubectl`.
```
kubectl create secret generic bigip-login --namespace kube-system --from-literal=username=BIG-IP_USERNAME--from-literal=password=PASSWORD --from-literal=url=BIG-IP_URL
```

### Step 2
Scale the cluster down to similuate an failed cluster node.
```
gcloud container clusters resize CLUSTER_NAME --node-pool NODE_POOL --size SIZE
```

