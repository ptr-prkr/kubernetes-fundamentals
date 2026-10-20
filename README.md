# Kubernetes Fundamentals

A hands-on DevOps project demonstrating Kubernetes deployment, networking, scaling and self-healing using K3s.

## Environment

- Ubuntu Server 24.04 LTS
- K3s / Kubernetes v1.36
- containerd
- Nginx
- kubectl

## Architecture

Client -> NodePort Service (30080) -> Kubernetes Deployment -> Nginx Pods

## Deployment

Apply the Kubernetes manifest:

    kubectl apply -f nginx.yaml

Verify the deployment:

    kubectl get deployments
    kubectl get pods -l app=nginx-demo
    kubectl get services

## Testing

    curl -I http://localhost:30080

Expected result: HTTP 200 OK.

## Scaling

    kubectl scale deployment nginx-demo --replicas=4

Kubernetes increases the number of running pods to four.

## Self-Healing

Deleting a pod causes Kubernetes to create a replacement automatically to maintain the desired replica count.

## Cleanup

    kubectl delete -f nginx.yaml

## Skills Demonstrated

- Kubernetes Pods
- Deployments
- Services and NodePort networking
- kubectl
- Horizontal scaling
- Self-healing
- Declarative configuration
