[**Pod**](https://kubernetes.io/docs/concepts/workloads/pods/pod/) is the smallest concept we have in Kubernetes. It is not a container. Pod consist of one or more containers.

[**Namespaces**](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/) - You can think of namespace as a virtual cluster inside of you Kubernetes cluster. You can have multiples namespaces inside of a singles Kubernetes cluster and they are isolated from each other. They can help you on your team with organisation, security and performance. Pods are running on namespaces

[**Label**](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/) is a metadata to identify information. It can be used for queries.

**Volume** serves data to the pod.

<p style="text-align:center;"><img src="/andresguisado/courses/kubernetes-basic-concepts/pods/assets/pod.png" alt="Pod"></p>


> **NOTE:** Don’t use naked Pods (that is, Pods not bound to a ReplicaSet or Deployment) if you can avoid it. Naked Pods will not be rescheduled in the event of a node failure. Fro further information in [Best Practices](https://kubernetes.io/docs/concepts/configuration/overview/)



