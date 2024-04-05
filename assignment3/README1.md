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

1. Apply the Nginx configuration:

   ```bash
   kubectl apply -f nginx-configmap.yaml

2. Deploy the Nginx configurations:

    ```bash
    kubectl apply -f nginx-dep.yaml
    kubectl apply -f nginx-svc.yaml
    kubectl apply -f app-1-dep.yaml
    kubectl apply -f app-1-svc.yaml
    kubectl apply -f app-2-dep.yaml
    kubectl apply -f app-2-svc.yaml

3. Apply the Ingress configurations:

    ```bash
    kubectl apply -f nginx-ingress.yaml
    kubectl apply -f app-1-ingress.yaml
    kubectl apply -f app-2-ingress.yaml
4. Get the nginx-service-ip by running the command:
    ```bash
    kubectl get svc nginx-svc
    kubectl get svc app-1-svc
    kubectl get svc app-2-svc

    Output:


5. Test the deployments and ingress configurations using curl:
    ```bash
    curl http://<nginx-service-ip>/nginx
    curl http://<nginx-service-ip>/app
    curl http://<nginx-service-ip>/app


This `README.md` file provides an overview of the contents of the repository, instructions for deployment, and testing steps using `curl` commands. You should customize it according to your specific requirements, providing any additional information or details necessary for users to understand and use the Kubernetes configurations effectively.
