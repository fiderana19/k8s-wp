# WordPress & MySQL Deployment on Kubernetes (K8s)

This project demonstrates a complete deployment of a WordPress application with a MySQL backend on a Kubernetes cluster. It uses standard K8s objects like Deployments, Services, Secrets, and Namespaces.

## 🚀 Project Overview

The architecture consists of:
*   **WordPress:** A frontend web server deployment.
*   **MySQL:** A relational database to store WordPress content.
*   **Networking:** ClusterIP for internal DB communication and NodePort for external web access.
*   **Configuration:** Managed via Kubernetes Secrets and Kustomize.

---

## 🛠️ Prerequisites

*   A running Kubernetes cluster.
*   `kubectl` command-line tool installed and configured.
*   Docker: optional, for local image management.

## 📂 Project Structure

```text
K8S-WP/
├── app-wordpress-namespace.yml
├── app-wordpress-secret.yml
├── mysql-deployment.yml
├── service-clusterip-mysql.yml
├── wordpress-deployment.yml
├── service-nodeport-wordpress.yml
├── kustomization.yml
```

---

## 🚀 Deployment Steps

Using **Kustomize**, we can deploy all resources defined in `kustomization.yml` with a single command:

```bash
kubectl apply -k .
```

---

## 🔍 Verification

Getting the namespace:

```bash
kubectl get namespace
```
<p align="center">
<img src="https://github.com/fiderana19/k8s-wp/blob/main/images/namespace.png?raw=true" alt="Namespace" width="800"/>
</p>

Getting the pods:

```bash
kubectl get po -n wordpress
```
<p align="center">
<img src="https://github.com/fiderana19/k8s-wp/blob/main/images/pods.png?raw=true" alt="Pods" width="800"/>
</p>

Getting the services:

```bash
kubectl get svc -n wordpress
```
<p align="center">
<img src="https://github.com/fiderana19/k8s-wp/blob/main/images/svc.png?raw=true" alt="Service" width="800"/>
</p>

Getting the secret:

```bash
kubectl get secret -n wordpress
```
<p align="center">
<img src="https://github.com/fiderana19/k8s-wp/blob/main/images/secret.png?raw=true" alt="Secret" width="800"/>
</p>

Getting the deployments:

```bash
kubectl get deployment -n wordpress
```
<p align="center">
<img src="https://github.com/fiderana19/k8s-wp/blob/main/images/deployment.png?raw=true" alt="Deployment" width="800"/>
</p>

---

## 🌍 Accessing WordPress

Once the pods are running, you can access the WordPress installation wizard via the NodePort service.
Open the machine Ip address and the Nodeport. 

<p align="center">
<img src="https://github.com/fiderana19/k8s-wp/blob/main/images/ip.png?raw=true" alt="Browser" width="800"/>
</p>

-----

## ⭐️ Star

Don't hesitate to give a star, it will gives me a motivation for my projects and my progress.