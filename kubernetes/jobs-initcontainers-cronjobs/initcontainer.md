[Init Container](https://kubernetes.io/docs/concepts/workloads/pods/init-containers/) is a container which is executed before the app container is started. `Init-containers` are usually used for deploying utilities or execute scripts which are not presented in the app image and it needs to run.

## Create a Pod with an init container

Look at the file `init-container.yaml`{{open}}. 

This example runs an `init-container` which creates a helloworld file in a volume and an application pod will be scheduled if the helloworld file exist in a specific path and it can read it.

Create the init container:

`kubectl apply -f /manifests/init-container.yaml`{{execute}}

It could get some time until the init container finish successfully and the pod run.

### Pod status

Init container get some time until it creates the file so you could have to check the status of the pod couple of times:

`kubectl get pods`{{execute}}

If the pod is running means that the file was created and the pod can read it.

We are going to check manually that the file is there with the correct content:

`kubectl exec -ti happypanda -- cat /opt/workdir/helloworld `{{execute}}

You should see a result like:

`The app is running`

### Delete Pod

`kubectl delete -f /manifests/init-container.yaml`{{execute}}

or 

`kubectl delete pod happypanda`{{execute}}