# F5 Kubernetes BIG-IP Controller Demo

## Introduction

This demo uses F5's bigip-k8s-ctlr to manage virtual servers, pools, and nodes on BIG-IPs for services running on Kubernetes clusters. More infomation on F5 BIG-IPs can be found at https://support.f5.com/kb/en-us/products/big-ip_ltm/manuals/product/ltm_configuration_guide_10_0_0.html.
The demo below if very high touch. Expect to do a lot of typing. 

## Prerequisites
To use this demo you will need the following
* kubectl
* A running Kubernetes cluster
* A working F5 BIG-IP LTM with administrative access to a named partition

## Running the demo

### Step 1
Using kubectl, create a Kubernetes secret containing the BIG-IP username, password, and URL.
```
kubectl create secret generic bigip-login --namespace kube-system --from-literal=username=BIG-IP_USERNAME--from-literal=password=PASSWORD --from-literal=url=BIG-IP_URL
```

### Step 2
Scale the cluster down to similuate an failed cluster node.
```
gcloud container clusters resize CLUSTER_NAME --size SIZE
```

