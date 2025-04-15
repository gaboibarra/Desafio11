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

minikube start --driver=hyperv --memory=2048 --hyperv-virtual-switch="Default Switch"
![image](https://github.com/user-attachments/assets/3f6acbd4-beef-4475-bb4e-1989127e4e1a)


### ✅ 2. Despliegue de MongoDB
#### Aplicar los manifiestos de MongoDB

```bash
kubectl apply -f .k8s/mongo-secret.yml
```
![image](https://github.com/user-attachments/assets/a74e5346-c139-4d46-8edb-e3b4e1cd90df)

```bash
kubectl apply -f .k8s/mongo-pvc.yml
```
![image](https://github.com/user-attachments/assets/f0919dbe-3909-422f-82a2-52dcfd6fa695)

```bash
kubectl apply -f .k8s/mongo-deployment.yml
```
![image](https://github.com/user-attachments/assets/b35518c5-d7b9-4e8d-a1f8-4952c2152ed9)

```bash
kubectl apply -f .k8s/mongo-service.yml
```
![image](https://github.com/user-attachments/assets/e1cd67ec-9147-472a-af22-163fc429c5e6)






```bash
docker build -t educacionit-app:latest ./educacionit-app
```


kubectl apply -f .k8s/app-config.yml
kubectl apply -f .k8s/app-deployment.yml
kubectl apply -f .k8s/app-service.yml


kubectl rollout restart deployment educacionit-app

kubectl get pods

kubectl get svc

minikube service educacionit-app
