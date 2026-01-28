# Notes App Helm Charts

This repository contains **Helm charts** for deploying a **multi-microservice Notes application** on Kubernetes.  
It is designed to provide a clean, modular, and production-ready way to deploy application services using Helm.

The Helm chart manages the deployment of multiple microservices such as frontend, backend, authentication, and database components, with support for environment-specific configurations.

---

## 📁 Repository Structure

```
Notes-App-Helm
├── Chart.lock
├── charts
│   ├── auth-service
│   │   ├── Chart.yaml
│   │   ├── templates
│   │   │   ├── configmap.yaml
│   │   │   ├── deployment.yaml
│   │   │   ├── hpa.yaml
│   │   │   ├── secret.yaml
│   │   │   └── service.yaml
│   │   └── values.yaml
│   ├── backend-service
│   │   ├── Chart.yaml
│   │   ├── templates
│   │   │   ├── configmap.yaml
│   │   │   ├── deployment.yaml
│   │   │   ├── hpa.yaml
│   │   │   ├── secret.yaml
│   │   │   └── service.yaml
│   │   └── values.yaml
│   ├── frontend-service
│   │   ├── Chart.yaml
│   │   ├── templates
│   │   │   ├── deployment.yaml
│   │   │   ├── hpa.yaml
│   │   │   └── service.yaml
│   │   └── values.yaml
│   └── mysql
│       ├── Chart.yaml
│       ├── templates
│       │   ├── configmap.yaml
│       │   ├── secret.yaml
│       │   ├── service.yaml
│       │   └── statefulset.yaml
│       └── values.yaml
├── Chart.yaml
├── README.md
├── templates
│   └── ingress.yaml
└── values.yaml

11 directories, 30 files

```

---

## 🚀 Deploy with Helm

1️⃣ Clone the repository
```
git clone https://github.com/AZAL-KHAN/Notes-App-Helm.git
cd Notes-App-Helm
```

## 2️⃣ Create namespace
```
kubectl create namespace notes-app
```

## 3️⃣ Update Helm dependencies
```
helm dependency update
```

## 4️⃣ Install the Helm chart
```
helm install notes-app . \
  --namespace notes-app
```

## 🔄 Upgrade / Redeploy (CI/CD friendly)

```
helm upgrade notes-app . \
  --namespace notes-app \
  --set-string auth.image.tag=V1 \
  --set-string backend.image.tag=V1 \
  --set-string frontend.image.tag=V1
```

## 🔍 Verify Deployment
```
helm list -n notes-app
kubectl get pods -n notes-app
kubectl get svc -n notes-app
```

## 🧹 Cleanup
```
helm uninstall notes-app -n notes-app
```