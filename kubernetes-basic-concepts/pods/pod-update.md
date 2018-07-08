We are going to update our happypanda pod running in **dev-service1** namespace and to do that you need to apply ```pod-update.yaml```.

Look at the file `/pod-update.yaml`{{open}}:

1. Pods labels has been added in the metadata section
2. Container image has been updated in the containers section 
3. Pod ports has been added in the containers section


### Update Pod 

A pod can be updated by applying a yaml file, let's apply our ```pod-update.yaml``` file with the above changes:

`kubectl apply -f pod-update.yaml`{{execute}}


### Didn't it work? What happend?

The error we are getting is the following:

```
The Pod "happypanda" is invalid: spec: Forbidden: pod updates may not change fields other than `spec.containers[*].image`, `spec.initContainers[*].image`, `spec.activeDeadlineSeconds` or `spec.tolerations` (only additions to existing tolerations)
```

Ok, let's review the [Kubernetes API Reference](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.10/#container-v1-core) and we can find the following statement in containers ports specification:

<p style="text-align:center;"><img src="/andresguisado/courses/kubernetes-basic-concepts/pods/assets/ports.png" alt="Ports"></p>


In Kubernetes, there're some fields can't be updated. Kubernetes API Reference is helping you out to know the API restrictions and the exact object specification which are available.

In order to update those forbidden updates, we should delete the pod and create it up again.
We could bypass these situations with "deployments" which we will cover in other chapter.

### Fixing it 

Delete the pod:

`kubectl delete pod happypanda -n dev-service1`{{execute}}

Apply the yaml file:

`kubectl apply -f pod-update.yaml`{{execute}}

Check it out:

`kubectl describe pod happypanda --namespace dev-service1`{{execute}}

Our happypanda pod is now running with labels, port specification and a new container image!

`kubectl get pod -n dev-service1`{{execute}}

