\# Lab 3 – Reflection

Mohamed Ahmed Abd-Elkader (SE3)



This lab deploys a containerized Python Flask application on Kubernetes

using Minikube

We create a Deployment with 3 replicas, and observe self-healing behavior.





pods: The smallest deployable unit. We deployed 3 Pods to allow load distribution and redundancy.



A Deployment manages the desired state (e.g., 3 replicas). If a Pod dies,

the Deployment controller automatically creates a replacement.



A Service provides a stable network endpoint. Clients connect to the Service

IP, and Kubernetes load-balances across available Pods.



configmap:

Externalizes configuration from the container image



When I deleted a Pod ,Kubernetes detected that the actual state (2 pods) differed from the desired state (3 pods)

and automatically created a new Pod within seconds.





Liveness Probe: Checks if the app is alive; restarts the container if it fails

Readiness Probe: Checks if the app is ready to receive traffic





Kubernetes manages application lifecycle automatically

Container health probes enable automatic recovery

Scaling is as simple as changing the `replicas` value

