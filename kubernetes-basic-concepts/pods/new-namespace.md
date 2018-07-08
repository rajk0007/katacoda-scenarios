Create a namespace can be done by a single command. 

Let's create **dev-service1** namespace:

`kubectl create namespace dev-service1`{{execute}}

Or you can create a YAML file and apply it, just like any other Kubernetes resource.

Look at the file `test-namespace.yaml`{{open}}

Create test namespace:

`kubectl apply -f test-namespace.yaml`{{execute}}

List namespaces up:

`kubectl get namespaces`{{execute}}

## Delete a Namespace

To delete a namespace there are two options, we can use a yaml file or a single command:

`kubectl delete -f test-namespace.yaml`{{execute}}

 or 
 
`kubectl delete namespace test`{{execute}}

Check test namespaces has been successfully deleted:

`kubectl get namespaces`{{execute}}

>**Note:** We are not going to remove ```dev-service1``` namespace as we will use it.

