# Cheatsheet - Kubernetes 
## Pods:
 - kubectl create pod <pod-name> --image=<image-name>: Create a pod using a specified image.
 - kubectl get pods: List all pods in the current namespace.
 - kubectl describe pod <pod-name>: Get detailed information about a specific pod.
 - kubectl delete pod <pod-name>: Delete a pod.
  
## Deployments:

 - kubectl create deployment <deployment-name> --image=<image-name>: Create a deployment using a specified image.
 - kubectl get deployments: List all deployments in the current namespace.
 - kubectl describe deployment <deployment-name>: Get detailed information about a specific deployment.
 - kubectl scale deployment <deployment-name> --replicas=<replica-count>: Scale the number of replicas for a deployment.
 - kubectl delete deployment <deployment-name>: Delete a deployment.
## Services:

 - kubectl expose deployment <deployment-name> --port=<port-number>: Expose a deployment as a service on a specified port.
 - kubectl get services: List all services in the current namespace.
 - kubectl describe service <service-name>: Get detailed information about a specific service.
 - kubectl delete service <service-name>: Delete a service.
## Namespaces:

 - kubectl create namespace <namespace-name>: Create a new namespace.
 - kubectl get namespaces: List all namespaces in the cluster.
 - kubectl describe namespace <namespace-name>: Get detailed information about a specific namespace.
 - kubectl delete namespace <namespace-name>: Delete a namespace.
## Configuration:

 - kubectl apply -f <config-file.yaml>: Apply the configuration from a YAML file.
 - kubectl get <resource-type>: List all resources of a specific type.
 - kubectl describe <resource-type> <resource-name>: Get detailed information about a specific resource.
 - kubectl delete <resource-type> <resource-name>: Delete a specific resource.
## Other useful commands:

 - kubectl logs <pod-name>: View the logs of a specific pod.
 - kubectl exec -it <pod-name> -- <command>: Execute a command inside a pod.
 - kubectl port-forward <pod-name> <local-port>:<pod-port>: Forward a local port to a port inside a pod.

This cheat sheet covers some of the most commonly used commands in Kubernetes, but it's important to note that Kubernetes is a vast and complex system. For more in-depth understanding and advanced usage, you may need to refer to the official Kubernetes documentation.
