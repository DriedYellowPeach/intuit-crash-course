# Deployment

## Overview

The application is containerized with Docker and deployed to Kubernetes. This mirrors Intuit's use of IKS (Intuit Kubernetes Service) and CDD for deployments.

## Docker

### Backend

```dockerfile
FROM eclipse-temurin:21-jre-alpine
WORKDIR /app
COPY target/*.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
```

### Frontend

```dockerfile
FROM node:20-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

FROM nginx:alpine
COPY --from=build /app/dist /usr/share/nginx/html
EXPOSE 80
```

### Build Images

```bash
# Backend
cd backend && mvn clean package -DskipTests
docker build -t intuit-crash-course-backend .

# Frontend
cd frontend
docker build -t intuit-crash-course-frontend .
```

## Kubernetes

Manifests live in the `k8s/` directory.

### Components

| Manifest             | Resource                           |
|----------------------|------------------------------------|
| `backend.yaml`       | Deployment + Service for backend  |
| `frontend.yaml`      | Deployment + Service for frontend |
| `postgres.yaml`      | StatefulSet + Service for DB      |
| `redis.yaml`         | Deployment + Service for cache    |
| `ingress.yaml`       | Ingress for routing               |

### Deploy to minikube

```bash
# Start cluster
minikube start

# Apply manifests
kubectl apply -f k8s/

# Check status
kubectl get pods
kubectl get services

# Access the app
minikube service frontend-service
```

### Useful Commands

```bash
# View logs
kubectl logs -f deployment/backend

# Scale
kubectl scale deployment/backend --replicas=3

# Rollback
kubectl rollout undo deployment/backend
```
