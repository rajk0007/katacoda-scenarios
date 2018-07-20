**Namespaces** isolates pods to separate workloads from each other and it gives you the capability of setting up resource constrainsts on it. It could fit with environment segregation.

## Discover Kubernetes namespaces 

Let's take a look at the initial Kubernetes namespaces:

`kubectl get namespace`{{execute}}

By default, Kubernetes comes with three namespaces. We can see them here:

<p style="text-align:center;"><img src="/contino/courses/kubernetes-basic-concepts/pods/assets/namespaces.png" alt="Namespaces"></p>


### kube-system

This namespace has objects created by Kubernetes system:

`clear && kubectl get pods -n kube-system`{{execute}}

Pods inside of this namespace are associated with services needed by Kubernetes in order to work. These consist of micro-services such as controllers and add-ons natively integrated with Kubernetes. Usually each cloud provider will run specific implementation pods in this namespace too - so don't worry if the `kube-system` namespace differs between clusters/cloud providers.

### kube-public

This namespace has a `ConfigMap` which contains the [bootstrapping and certificate](https://kubernetes.io/docs/reference/access-authn-authz/bootstrap-tokens/) information for the Kubernetes cluster:

`clear && kubectl get pods -n kube-public`{{execute}}

You won't see anything running in this namespace, but we can see a `cluster-info` ConfigMap:

`clear && kubectl get configmap -n kube-public cluster-info -o yaml`{{execute}}

In addition, this namespace might be treated as somewhere used to run an object which should be visible and readable throughout the whole cluster.

### default

Kubernetes creates this namespace by default. All objects created without specifying a namespace will automatically be created in the `default` namespace.

This namespace is empty and doesn't contain any objects:

`clear && kubectl get pods -n default`{{execute}}

One thing to note about the `default` namespace is that it can't be deleted, unlike other namespaces within the Kubernetes cluster.