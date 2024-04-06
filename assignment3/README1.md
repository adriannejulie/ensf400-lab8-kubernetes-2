# Kubernetes Deployment and Ingress Example

This repository contains Kubernetes YAML files for deploying Nginx and two sample applications (`app-1` and `app-2`) along with Ingress configurations for routing traffic to these applications.

## Files

1. `nginx-dep.yaml`: Deployment YAML file for Nginx.
2. `nginx-configmap.yaml`: ConfigMap YAML file for Nginx configuration.
3. `nginx-svc.yaml`: Service YAML file for Nginx.
4. `nginx-ingress.yaml`: Ingress YAML file for routing traffic to Nginx and the sample applications.
5. `app-1-dep.yaml` and `app-1-svc.yaml`: Deployment and Service YAML files for `app-1`.
6. `app-2-dep.yaml` and `app-2-svc.yaml`: Deployment and Service YAML files for `app-2`.
7. `app-1-ingress.yaml` and `app-2-ingress.yaml`: Ingress YAML files for routing traffic to `app-1` and `app-2`.

## Instructions
1. Start Minikube
    ```bash
    minikube start

1. Apply all YAML files:

   ```bash
    kubectl apply -f .

3. Ensure all pods are working
    ```bash
    kubectl get deployments

5. Test the deployments and ingress configurations using curl:
    ```bash
    curl http://$(minikube ip)/


This `README.md` file provides an overview of the contents of the repository, instructions for deployment, and testing steps using `curl` commands. You should customize it according to your specific requirements, providing any additional information or details necessary for users to understand and use the Kubernetes configurations effectively.


kubectl delete -f .