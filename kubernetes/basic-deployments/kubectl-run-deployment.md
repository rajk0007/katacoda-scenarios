### High Level View of Deployments

Kubernetes deployments manage stateless services running in your cluster (as opposed to, for example StatefulSets, which manage stateful services). Their purpose is to keep a set of identical pods running and upgrade them in a controlled way – performing a rolling update by default. There are different deployment strategies that work with Deployments. They are, however, out of scope of this scenario. For more information on deployment strategies, read the [Kubernetes Documentation](#link).

![Deployments - High Level Overview](assets/deployment-high-level.png)