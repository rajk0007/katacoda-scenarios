[**Pod**](https://kubernetes.io/docs/concepts/workloads/pods/pod/) is the smallest concept we have in Kubernetes. It is not a container. Pods consist of one or more containers.

You can think of a [**Namespace**](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/) as a virtual cluster inside of you Kubernetes cluster. You can have multiple namespaces inside of a single Kubernetes cluster and they are isolated from each other. They can help your team with organisation, security and performance. All pods run inside namespaces.

A [**Label**](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/) is a key/value pair that provides attributes to objects. It's good practice to use labels as much as possible, as you'll be able to have more granular control over what your pods are doing. Labes can be used to query specific objects.

A **Volume** serves data to the pod.

<p style="text-align:center;"><img src="/contino/courses/kubernetes/pods/assets/pod.png" alt="Pod"></p>

> **NOTE:** Don’t use naked Pods (that is, Pods not bound to a ReplicaSet or Deployment) if you can avoid it. Naked Pods will not be rescheduled in the event of a node failure. For further information, refer to the Kubernetes [Best Practices](https://kubernetes.io/docs/concepts/configuration/overview/#naked-pods-vs-replicasets-deployments-and-jobs) documentation.
