# kubernetes

## Definition and why we need it.

Kubernetes is a portable, extensible, open source platform for container orchestration.

Kubernetes automates operational tasks of container management and includes built-in commands for deploying applications, rolling out changes to your applications, scaling your applications up and down to fit changing needs, monitoring your applications, and more—making it easier to manage applications.

## Docker

Docker is an open platform for developing, shipping, and running applications.

Docker allows you to separate your applications from your infrastructure so you can deliver software quickly. With Docker, you can manage your infrastructure in the same ways you manage your applications.

By taking advantage of Docker's methodologies for shipping, testing, and deploying code quickly, you can significantly reduce the delay between writing code and running it in production.

## why kubernetes

Demand for a proper way of managing large scale of containers.

## kubernetes features

1. High availability or no downtime.
2. Scalability of high performance.
3. Disaster recovery - backup and restore.

## kubernetes components

1. pod: an abstraction over container, smallest unit of k8s, each pod get its own IP address. (k8s create virtual networking.)
2. node: a node is a single worker machine within a Kubernetes cluster, responsible for running the actual applications and workloads.
3. cluster: a Kubernetes cluster is the overarching architecture that organizes and manages a collection of nodes, networks, and resources required to run applications.
4. service: a Service defines a logical grouping of Pods and exposes them through a single, stable IP address. It automatically manages routing and load balancing to distribute traffic across the set of Pods, even if Pods are dynamically created or removed.

- ClusterIP: Exposes the Service only within the cluster, using an internal IP address.
- NodePort: Exposes the Service on a specific port on each node in the cluster, making it accessible externally.
- LoadBalancer: Provisions an external load balancer (if supported by the cloud provider) and assigns it to the Service.
- ExternalName: Maps the Service to an external DNS name, allowing access to resources outside the cluster.

5. ingress: Ingress in Kubernetes is used for managing and routing external HTTP/HTTPS traffic to services within the cluster.
6. ConfigMap: external configuration of your application.
7. Secret: ConfigMap saved in base64 encoded format.
8. Volumes: Volumes are storage abstractions that allow Pods to persist data across container restarts.

- Persistent Volume (PV): Represents the actual storage resource, which can come from an NFS, cloud disk, or other storage backends.
- Persistent Volume Claim (PVC): A request by a Pod to use a PV. When a PVC is created, Kubernetes attempts to bind it to an available PV or dynamically provision one based on a StorageClass.

9. Deployments: blueprint for pods with replica mechanism, which is designed for stateless applications, where each instance (or replica) of the application is identical and does not rely on a specific identity or stable storage.
10. StatefulSet: A StatefulSet is designed for stateful applications that require stable identities, persistent storage, or ordered deployment and scaling.

## kubernetes architecture

- Control Plane (Master Node):
  - API Server/ Kubernetes Dashboard (UI) / CLI --> Entrypoint to k8s cluster.
  - Scheduler --> ensure pods placement.
  - Controller Manager --> keeps track of what is happening in the cluster.
  - etcd --> hold aktuelle status of kubernetes cluster.
- 4 processes must run on master node:
  - API server (gateway)
  - Scheduler
  - Controller manager
  - etcd (cluster brain --> key value store, store the information of cluster)
- Worker nodes (Slave Node):
  each node contains multiple pods:
  - pod-1: backend app
  - pod-2: DB
- 3 processes must run on each worker Node:
  - container runtime
  - kubelet
  - kube proxy
- Virtual networks.
  enable to the communication between master and worker nodes.

## kubernetes configuration

- metadata
- spec
- status
