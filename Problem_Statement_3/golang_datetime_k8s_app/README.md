# Golang Date & Time Web App

This is a simple GoLang web application that displays the current date and time. The app is containerized using Docker and deployed to Kubernetes with two replicas using a declarative configuration.

## 🛠 Technologies Used
- GoLang
- Docker
- Kubernetes (Declarative YAML)
- DockerHub (for container image hosting)

## 📁 Project Structure

```
golang_datetime_k8s_app/
├── main.go              # Go web server showing date and time
├── Dockerfile           # Dockerfile to containerize the app
├── deployment.yaml      # Kubernetes deployment with 2 replicas
└── service.yaml         # Kubernetes LoadBalancer service
```

## 🚀 Getting Started

### 1. Build and Push Docker Image
```bash
docker build -t your_dockerhub_username/golang-datetime-app .
docker push your_dockerhub_username/golang-datetime-app
```

### 2. Deploy to Kubernetes
```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

### 3. Access the App
- If using **Minikube**: `minikube service datetime-service`
- If using **cloud provider**: Use the external IP provided by LoadBalancer

## ✨ Output
You will see a message like:
```
Current Date & Time: 2025-04-04 18:45:23
```

---

Created as part of a Kubernetes + GoLang technical assessment.