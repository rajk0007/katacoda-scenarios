**Namespaces** isolates pods to separate workloads from each other and give you the capability of setting up resource constrainsts on it. It could fit with environment segregation.


## Discover Kubernetes namespaces 

Let's take a look at the initial Kubernetes namespaces:

`kubectl get namespace`{{execute}}

We can see three namespaces as follows:

<p style="text-align:center;"><img src="/andresguisado/courses/kubernetes-basic-concepts/pods/assets/namespaces.png" alt="Namespaces"></p>


### kube-system

This namespace has objects created by Kubernetes system:

`clear & kubectl get pods -n kube-system`{{execute}}

Those systems are needed to make Kubernetes works, such as controllers and add-ons natively integrated with Kubernetes.

### kube-public

This namespace just contains a configmap which has the [bootstrapping and certificate](https://kubernetes.io/docs/reference/access-authn-authz/bootstrap-tokens/) information of the K8s cluster:

`clear & kubectl get pods -n kube-public`{{execute}}

You don't see anything running in this namespace but we can see a ```cluster-info``` configmap:

`clear & kubectl get configmap -n kube-public  cluster-info -o yaml`{{execute}}

In addtion, this namespace might be treated as a namespace to run any object which should be visible and readable throughout the whole cluster since it is visible and readable from all parts of the Kubernetes cluster.

### default
Kubernetes sets this namespaces out of the box to use it for objects with no other namespace:

`clear & kubectl get pods -n default`{{execute}}

It is empty from the beginning and it doesn't have anyting special, except you can't delete it.