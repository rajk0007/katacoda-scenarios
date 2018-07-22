`Node affinity` allows you to schedule pods on selective nodes. But what if you want to run pods along with other pods selectively? **`Pod affinity`** helps us with that.

>**Note**: It is a beta feature, we won't run any exercise of it but we will get through the basic concepts, for further info read [Affinity and Anti-Affinity](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#affinity-and-anti-affinity)

### Pod Affinity
Look at the [API Kubernetes Reference](https://v1-10.docs.kubernetes.io/docs/reference/generated/kubernetes-api/v1.10/#podaffinity-v1-core)

The two main `specs` for Pod Afiinity are:

* `spec.affinity.podAffinity.preferredDuringSchedulingIgnoredDuringExecution`is for **Soft Pod Affinity**. If the preferred option is available, the Pod will run there. If not, the Pod can still be sheduled elsewhere. 

* `spec.affinity.podAffinity.requiredDuringSchedulingIgnoredDuringExecution` is for **Hard Pod Affinity**. If the required option is not available, the Pod cannot run.


### Hard Pod Affinity

Look at the file `pod-hard-affinity.yaml`:

`cat /manifests/pod-hard-affinity.yaml`{{execute}}

<p style="text-align:center;"><img src="/andresguisado/courses/kubernetes/assign-pod-nodes/assets/pod-hard-affinity.png" alt="pod-hard-affinity"></p>

This is a `hard pod affinity`. If none of the node has a pod running with label **fruit=apple**, the pod will not be scheduled at all. Here **topologyKey** is a label of a node. This can be any node label.

### Soft Pod Affinity

Soft Pod Affinity will schedule the Pod even though is not finding a pod running with label **fruit=apple**.

### Pod Anti-Affinity

Look at the [API Kubernetes Reference](https://v1-10.docs.kubernetes.io/docs/reference/generated/kubernetes-api/v1.10/#podantiaffinity-v1-core0)


The two main `specs` for Pod Anti-Afiinity are:

* `spec.affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution`is for **Soft Pod Anti-Affinity**. If the preferred option is available, the Pod will run there. If not, the Pod can still be sheduled elsewhere. 

* `spec.affinity.podAntiAffinity.requiredDuringSchedulingIgnoredDuringExecution` is for **Hard Pod Anti-Affinity**. If the required option is not available, the Pod cannot run.

`Pod anti-affinity` works the opposite way of pod affinity. If one of the nodes has a pod running with label **fruit=apple**, the pod will be scheduled on different node.

