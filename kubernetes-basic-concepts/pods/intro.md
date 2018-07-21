[**Pod**](https://kubernetes.io/docs/concepts/workloads/pods/pod/) is the smallest concept we have in Kubernetes. It is not a container. Pods consist of one or more containers.

[**Namespaces**](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/) - You can think of namespace as a virtual cluster inside of you Kubernetes cluster. You can have multiples namespaces inside of a single Kubernetes cluster and they are isolated from each other. They can help your team with organisation, security and performance. Pods run inside of namespaces.

[**Label**](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/) is a metadata to identify information. It can be used for queries. It's good practice to use labels as much as possible, as you'll be able to have more granular control over what your pods are doing.

**Volume** serves data to the pod.

<p style="text-align:center;"><img src="/contino/courses/kubernetes-basic-concepts/pods/assets/pod.png" alt="Pod"></p>

> **NOTE:** Don’t use naked Pods (that is, Pods not bound to a ReplicaSet or Deployment) if you can avoid it. Naked Pods will not be rescheduled in the event of a node failure. For further information, refer to the Kubernetes [Best Practices](https://kubernetes.io/docs/concepts/configuration/overview/) documentation.
