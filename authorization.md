# Authorization model for an on-premises Kubeflow setup

> Model on how to handle resource sharing between different users on a shared Kubeflow system

To facilitate sharing and isolation of resources, Kubeflow uses Kubernetes _namespaces_. Each namespace represents a Kubeflow **profile**, which in turn has the needed Kubernetes resources to do it's work. To access resources for a specific profile through the Web UI, Kubeflow uses [json web tokens(JWT)](https://jwt.io). These are passed with every authenticated request and contain the needed authorization information for the profile.

## Access to resources

There are two ways a user can access resources in Kubeflow. Through low and high level services:

1. _Low level services_ : Here, the user uses `kubectl` and applies custom resource definitions directly to it's resources.
   - For example through `kubectl`: `kubectl apply -f tfjob`
2. _High level services_ : Here, the user uses the Kubeflow web UI to access resources.
   - For example the jupyter notebook UI

![](./attachments/Pasted%20image%2020211129202407.png) [^1]

## References

- https://www.kubeflow.org/docs/components/multi-tenancy/design/

[^1]: In depth [authentication](../authentication/authentication.md) and [authorization](authorization.md) walk through: https://youtu.be/qyUyYLvmKHY
