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
- 📰 Powershell

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

#### Pod de MongoDB Running

![image](https://github.com/user-attachments/assets/9f403adc-02ab-4fbb-8809-3626e36045cc)

### ✅ 2. Despliegue de la Aplicacion
#### Ubicarse en la carpeta con el Dockerfile: (En este caso Desafio11 previamente hice una copia de Desafio10 para trabajar mejor)

![image](https://github.com/user-attachments/assets/b430ae6b-0974-499f-b8ce-aad30ec6758f)

#### Construir la imagen (Antes de esto se debe configurar Docker para usar el demonio de Minikube de esta manera le digo a Docker que use el entorno interno de Minikube)

![image](https://github.com/user-attachments/assets/a4307653-e5ff-43ee-9d90-522d3b1aedf4)

#### Ahora si se puede construir la imagen

![image](https://github.com/user-attachments/assets/c480df1e-f1f3-432f-8fae-90bcb02b59f8)

#### Cargar la imagen a Minikube

![image](https://github.com/user-attachments/assets/ecc7543e-ffcf-4285-b158-83364e7f2378)

#### ❗Reiniciar un despliegue en Kubernetes sirve para forzar que los pods del Deployment se reinicien para usar esa nueva imagen

### Aplicar los manifiestos de la App
```bash
kubectl apply -f .k8s/app-config.yml
```
![image](https://github.com/user-attachments/assets/e66b4928-1f5f-4c82-92cf-bef9daeb1487)

```bash
kubectl apply -f .k8s/app-deployment.yml
```
![image](https://github.com/user-attachments/assets/c1bf3071-5413-4e1a-9fbb-b8e105ad40b4)

```bash
kubectl apply -f .k8s/app-service.yml
```
![image](https://github.com/user-attachments/assets/eae41630-a61b-4d40-8a5b-63829f0fe149)

#### Pod de la App Running

![image](https://github.com/user-attachments/assets/939a26c8-bb8b-41b7-94c2-714982896617)

### ✅ 3.Acceder a la app

![image](https://github.com/user-attachments/assets/fe4cb019-c93f-4f36-b577-405583d7df9b)

#### App en funcionamiento

![image](https://github.com/user-attachments/assets/e8c11ef5-a637-42bc-9961-53cde32cf4b5)

