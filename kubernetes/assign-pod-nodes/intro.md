 You can manually assign pods to a specific node cluster, it is not necessary as the scheduler is doing that automatically for you but it might be some circumstances where you may want more control on this, e.g. to ensure that a pod ends up on a machine with an SSD attached to it.

There're different ways to achive that, `nodeSelector, Affinity and Anti-Affinity`, and they all use [Labels and Selectors](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/). 

This scenario provides an overall view of how to assign pods to nodes by using `nodeSelector`. The `Affinity and Anti-Affinity` features are still in beta mode thus we will just mention them.

For further info read [Assigning Pods to Nodes](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/).






