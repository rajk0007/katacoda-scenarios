**Namespaces** is the way to isolate Pods in order to separate workloads from each other and set up resource constrainsts. It could fit with environment segregation as well. Kubernetes has a default namespace called kube-system.

## Tasks

Create **contino** namespace:

`kubectl create namespace contino`{{execute}}

## Validation

**List namespaces up:**

`kubectl get namespaces`{{execute}}