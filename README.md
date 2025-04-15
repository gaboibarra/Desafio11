# 🚀 Desafío #11 - Kubernetes Deployment (Minikube + MongoDB + Node.js)

Este desafío consistió en transformar un entorno Docker Compose a Kubernetes, desplegando una aplicación Node.js conectada a MongoDB utilizando Minikube.

---

## 📁 Estructura del proyecto

Desafio11/ 
├── .k8s/ # Archivos YAML para Kubernetes │ ├── mongo-secret.yaml │ ├── mongo-pvc.yaml │ ├── mongo-deployment.yaml │ ├── mongo-service.yaml │ ├── app-config.yaml │ ├── app-deployment.yaml │ ├── app-service.yaml ├── educacionit-app/ # Código fuente de la app │ ├── Dockerfile │ ├── package.json │ └── src/
