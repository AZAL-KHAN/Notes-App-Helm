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