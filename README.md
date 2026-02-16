# 🚀 Production-Ready DevOps Pipeline with Kubernetes, CI/CD & Monitoring

This project demonstrates an end-to-end DevOps workflow for building, deploying, and monitoring a containerized web application using modern DevOps tools and practices. The goal of this project is to simulate a production-like environment and showcase practical DevOps skills such as CI/CD automation, container orchestration, and observability.

---

## 📌 Project Overview

The project covers the complete lifecycle of an application:

- Source code management  
- Containerization of the application  
- Deployment on Kubernetes with multiple replicas  
- Automated CI/CD pipeline for build and deployment  
- Application and infrastructure monitoring  
- Centralized logging for troubleshooting  

This setup reflects how DevOps teams operate in real-world production systems.

---

## 🏗 High-Level Architecture

1. Developer pushes code to GitHub  
2. CI/CD pipeline builds Docker image  
3. Image is deployed to Kubernetes  
4. Kubernetes manages replicas and service networking  
5. Prometheus scrapes application and system metrics  
6. Grafana visualizes traffic, latency, and resource usage  
7. Logs are collected and used for debugging  

---

## 🔧 Tech Stack

- **Application**: Python (Flask)  
- **Containerization**: Docker  
- **Orchestration**: Kubernetes (Minikube for local setup)  
- **CI/CD**: Jenkins (can be adapted to GitHub Actions)  
- **Monitoring**: Prometheus, Grafana  
- **Logging**: Loki, Promtail  
- **Local Cluster**: Minikube  

---

## 🤔 Why This Stack

This stack was chosen to reflect tools commonly used in modern DevOps environments:

- Docker ensures consistent application packaging across environments.  
- Kubernetes handles deployment, scaling, and service management.  
- CI/CD automates build and deployment to reduce manual errors.  
- Prometheus and Grafana provide visibility into application performance and system health.  
- Centralized logging helps debug issues in distributed systems.

---

## ✅ Key Features

- Containerized web application deployed on Kubernetes  
- Rolling updates and multiple replicas for high availability  
- Automated build and deployment using CI/CD  
- Health checks and metrics endpoints exposed by the application  
- Real-time monitoring dashboards in Grafana  
- Centralized logging for easier debugging  

---

## 📸 Monitoring Output (Grafana)

The Grafana dashboard shows:

- HTTP requests per second  
- Request latency (P95)  
- Pod CPU usage  
- Pod memory usage  
- Number of running replicas  

> Screenshot available in the `screenshots/` folder.

---

## ▶️ How to Run Locally (Minikube)

```bash
minikube start
eval $(minikube docker-env)

docker build -t sample-flask:latest ./app

kubectl apply -f k8s/namespace.yaml
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml

kubectl -n devops-demo port-forward svc/sample-flask 8080:80
