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
2. Enable Ingress
    ```bash
    minikube addons enable ingress
1. Apply all YAML files:

   ```bash
    kubectl apply -f .
3. Ensure all pods are working
    ```bash
    kubectl get po
- Example output:
    ```bash
    NAME                         READY   STATUS    RESTARTS   AGE
    app-1-dep-86f67f4f87-s6rwr   1/1     Running   0          3m49s
    app-2-dep-7f686c4d8d-lhglt   1/1     Running   0          3m49s
    nginx-dep-74b4478f5f-btq8x   1/1     Running   0          3m48s
    nginx-dep-74b4478f5f-gfq7t   1/1     Running   0          3m48s
    nginx-dep-74b4478f5f-h9sxp   1/1     Running   0          3m48s
    nginx-dep-74b4478f5f-pzq79   1/1     Running   0          3m48s
    nginx-dep-74b4478f5f-wqndp   1/1     Running   0          3m48s

5. Test the deployments and ingress configurations using curl:
    ```bash
    curl http://$(minikube ip)/
- (Optional) Run 10 curl commands using:

    ```bash
    for i in $(seq 1 10); do curl -s $(minikube ip):80/ ; echo ; done
- Output
    ```bash
    Hello World from [app-2-dep-7f686c4d8d-lhglt]!
    Hello World from [app-1-dep-86f67f4f87-s6rwr]!
    Hello World from [app-2-dep-7f686c4d8d-lhglt]!
    Hello World from [app-1-dep-7f686c4d8d-lhglt]!
    Hello World from [app-1-dep-86f67f4f87-s6rwr]!
    Hello World from [app-1-dep-86f67f4f87-s6rwr]!
    Hello World from [app-1-dep-86f67f4f87-s6rwr]!
    Hello World from [app-1-dep-86f67f4f87-s6rwr]!
    Hello World from [app-2-dep-7f686c4d8d-lhglt]!
    Hello World from [app-1-dep-86f67f4f87-s6rwr]!

If you have any issues or READY from step 4 does not show 1/1, please run:
```bash
kubectl delete -f .
```
Then try again, starting from step 3.
