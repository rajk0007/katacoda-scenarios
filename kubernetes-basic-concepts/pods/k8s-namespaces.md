**Namespaces** isolates pods to separate workloads from each other and it gives you the capability of setting up resource constrainsts on it. It could fit with environment segregation.

## Discover Kubernetes namespaces 

Let's take a look at the initial Kubernetes namespaces:

`kubectl get namespace`{{execute}}

By default, Kubernetes comes with three namespaces. We can see them here:

<p style="text-align:center;"><img src="/contino/courses/kubernetes-basic-concepts/pods/assets/namespaces.png" alt="Namespaces"></p>


### kube-system

This namespace has objects created by Kubernetes system:

`kubectl get pods -n kube-system`{{execute}}


Pods inside of this namespace are needed to make Kubernetes works, such as controllers and add-ons natively integrated with Kubernetes which we will talk later on

> **Note:** Usually each cloud provider will run specific implementation pods in this namespace too - so don't worry if the `kube-system` namespace differs between clusters/cloud providers.

### kube-public

This namespace has a `ConfigMap` which contains the [bootstrapping and certificate](https://kubernetes.io/docs/reference/access-authn-authz/bootstrap-tokens/) information for the Kubernetes cluster:

`kubectl get pods -n kube-public`{{execute}}

You won't see anything running in this namespace, but we can see a `cluster-info` ConfigMap:

`kubectl get configmap -n kube-public cluster-info -o yaml`{{execute}}

In addition, this namespace might be treated as somewhere used to run an object which should be visible and readable throughout the whole cluster.

### default

All objects created without specifying a namespace will automatically be created in the `default` namespace.

This namespace is empty and doesn't contain any objects:

`kubectl get pods -n default`{{execute}}

One thing to note about the `default` namespace is that it can't be deleted, unlike other namespaces within the Kubernetes cluster.
