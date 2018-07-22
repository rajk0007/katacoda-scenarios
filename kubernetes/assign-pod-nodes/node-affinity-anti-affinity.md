In the previous exercice, we have introduced `nodeSelector`  but using this is a hard condition. If the condition is not met, the pod cannot be shceduled.
`Node/Pod Affinity and Anti-Affinity` solves this issue by introducing soft and hard conditions.

<p style="text-align:center;"><img src="/contino/courses/kubernetes/assign-pod-nodes/assets/type-affinity-anti-affinity.png" alt="Type_affinity_anti_affinity"></p>

>**Note**: It is a beta feature, we won't run any exercise of it but we will get through the basic concepts, for further info read [Affinity and Anti-Affinity](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#affinity-and-anti-affinity)

## Node Affinity

Look at the [API Kubernetes Reference](https://v1-10.docs.kubernetes.io/docs/reference/generated/kubernetes-api/v1.10/#nodeaffinity-v1-core)

The two main `specs` for Node Afiinity are:

* `spec.affinity.nodeAffinity.preferredDuringSchedulingIgnoredDuringExecution` is for **Soft Node  Affinity and Anti-Affinity**. If the preferred option is available, the Pod will run there. If not, the Pod can still be sheduled elsewhere. 

* `spec.affinity.nodeAffinity.requiredDuringSchedulingIgnoredDuringExecution` is for **Hard NodeAffinity and Anti-Affinity**. If the required option is not available, the Pod cannot run.

### Soft Node Affinity

Look at the file `node-soft-affinity.yaml`:

`cat /manifests/node-soft-affinity.yaml`{{execute}}

<p style="text-align:center;"><img src="/contino/courses/kubernetes/assign-pod-nodes/assets/node-soft-affinity.png" alt="node-soft-affinity"></p>

If there are no nodes labeled as apple, the pod would have still be scheduled.

### Hard Node Affinity

Look at the file `node-soft-affinity.yaml`:

`cat /manifests/node-hard-affinity.yaml`{{execute}}

<p style="text-align:center;"><img src="/contino/courses/kubernetes/assign-pod-nodes/assets/node-hard-affinity.png" alt="node-hard-affinity"></p>

If there are no nodes labeled as apple, the pod won't be scheduled.

## Node Anti-Affinity

Node `anti-affinity` can be achieved by using `NotIn` operator. This will help us to ignore nodes while scheduling.

Here is an example:

<p style="text-align:center;"><img src="/contino/courses/kubernetes/assign-pod-nodes/assets/node-anti-affinity.png" alt="node-anti-affinity"></p>

