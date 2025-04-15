# 🚀 Desafío #11 - Kubernetes Deployment (Minikube + MongoDB + Node.js)

Este desafío consistió en transformar un entorno Docker Compose a Kubernetes, desplegando una aplicación Node.js conectada a MongoDB utilizando Minikube.

---

## 📁 Estructura del proyecto

```bash
Desafio11/
├── .k8s/ # Archivos YML para Kubernetes
│ ├── mongo-secret.yml
│ ├── mongo-pvc.yml
│ ├── mongo-deployment.yml
│ ├── mongo-service.yml
│ ├── app-config.yml
│ ├── app-deployment.yml
│ ├── app-service.yml
├── educacionit-app/ # Código fuente de la app
│ ├── Dockerfile
│ ├── package.json
│ └── src/
```
---

## ⚙️ Tecnologías utilizadas

- 🐳 Docker
- ☸️ Kubernetes
- 📦 Minikube
- 🐘 MongoDB
- 🧠 NestJS (Node.js)
- 🖥️ Hyper-V (como driver)

---

## 🔄 Pasos para el despliegue

### ✅ 1. Iniciar Minikube

```bash
minikube start --driver=hyperv --memory=2048 --hyperv-virtual-switch="Default Switch"

kubectl apply -f .k8s/mongo-secret.yaml
kubectl apply -f .k8s/mongo-pvc.yaml
kubectl apply -f .k8s/mongo-deployment.yaml
kubectl apply -f .k8s/mongo-service.yaml

docker build -t educacionit-app:latest ./educacionit-app


kubectl apply -f .k8s/app-config.yaml
kubectl apply -f .k8s/app-deployment.yaml
kubectl apply -f .k8s/app-service.yaml


kubectl rollout restart deployment educacionit-app

kubectl get pods

kubectl get svc

minikube service educacionit-app
