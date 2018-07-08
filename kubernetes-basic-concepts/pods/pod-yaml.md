
To communicate with the Kubernetes API we use a CLI tool called ```kubectl``` but most likely you are going to use YAML files as well in order to create cluster configuration and objects.

In this YAML file, we are going to create a Pod specification to tell Kubernetes how to deploy and run it.

Let's begin!

## Kubernetes API Reference 

Every Kubernetes object has an API specification and this specification can be written it down in a YAML file.

In this exercise, we want to create a Pod and first of all, we are going to check the [Kubernetes API](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.10/#pod-v1-core) to check the Pod's full specification.

Kubernetes API Reference is helping us out to configure Kubernetes objects by yaml files. 

>**NOTE:** As an interesting fact, Kubernetes API is using [Swaggerv.1.2](https://swagger.io/) and [OpenAPI](https://www.openapis.org/) but fron Kubernetes v.1.10 Swaggerv is deprecated and it will get removed in Kubernetes v.1.14.

Look at the file `pod.yaml`{{open}}

The pod name is ```happypanda``` and it deploys a nginx container image from docker hub public registry.


## Create a Pod

By using the ```kubectl``` cli tool, we authenticate to the Kubernetes API and apply our Pod specification to the Kubernetes Cluster:

`kubectl apply -f /pods-manifests/pod.yaml`{{execute}}

## Validation

In order to validate if happypanda pod  is running, we need to ask the Kubernetes API as follows:

`kubectl get pods`{{execute}}

Notice that happypanda pod is running on the default namespace since we didn't set any namespace in our specification.

## Delete a Pod

We can delete Pods by using a yaml file or a single command:

`kubectl delete -f /pods-manifests/pod.yaml`{{execute}}

or 

`kubectl delete pod happypanda`{{execute}}

Check happypanda por has been deleted:

`kubectl get pods`{{execute}}
