# Kubernetes Python DevOps Project 🚀
[![GitHub stars](https://img.shields.io/github/stars/MaheshTirumalasetty/kubernetes-python-devops?style=social)](https://github.com/MaheshTirumalasetty/kubernetes-python-devops)
## Project Overview
A Python Django web application containerized with Docker
and deployed on Kubernetes with full DevOps pipeline.

## Tech Stack
- 🐳 Docker - Containerization
- ☸️ Kubernetes (minikube) - Container Orchestration
- 🌐 Nginx Ingress - Host-based routing
- 📊 Prometheus - Metrics collection
- 📈 Grafana - Visualization dashboards
- ⚙️ ConfigMaps - Configuration management
- 🔐 Secrets - Sensitive data management
- 📡 Kubeshark - Network traffic monitoring

## Project Structure
```
kubernetes-python-devops/
├── Dockerfile
├── requirements.txt
├── deployment.yml
├── service.yml
├── ingress.yml
├── cm.yml
└── devops/
    ├── manage.py
    ├── demo/
    │   └── templates/
    │       └── demo_site.html
    └── devops/
```

## Prerequisites
- Docker Desktop
- minikube
- kubectl
- helm

## How to Run

### Build and Deploy
```bash
# Build Docker image
docker build -t maheshf1/python-sample-app-demo:v1 .

# Load into minikube
minikube image load maheshf1/python-sample-app-demo:v1

# Deploy application
kubectl apply -f deployment.yml
kubectl apply -f service.yml
kubectl apply -f ingress.yml

# Apply ConfigMap and Secrets
kubectl apply -f cm.yml
kubectl create secret generic test-secret1 \
  --from-literal=db-port="YourSecretValue"
```

### Access Application
```bash
kubectl port-forward service/python-django-sample-app 8080:80
```
Open browser: http://localhost:8080/demo/

### Install Monitoring Stack
```bash
# Install Prometheus
helm repo add prometheus-community \
  https://prometheus-community.github.io/helm-charts
helm install prometheus prometheus-community/prometheus

# Install Grafana
helm repo add grafana https://grafana.github.io/helm-charts
helm install grafana grafana/grafana
```

### Access Monitoring
```bash
# Prometheus
kubectl port-forward svc/prometheus-server 9090:80
# Open: http://localhost:9090

# Grafana
kubectl port-forward service/grafana 3000:80
# Open: http://localhost:3000
```
## 🌟 What I Learned

This project was built while following the amazing DevOps courses by:

### 📚 Abhishek Veeramalla
- **YouTube:** [Free DevOps Course](https://www.youtube.com/@AbhishekVeeramalla)
- **Course:** Docker Zero to Hero & Kubernetes Beginner to Expert

> *"This hands-on project helped me understand real-world DevOps workflows 
> including containerization, Kubernetes orchestration, monitoring, 
> and GitOps practices."*
> — Mahesh Tirumalasetti

---

## 🏆 Key Achievements
- ✅ Dockerized a Python Django application from scratch
- ✅ Deployed on Kubernetes with 2 replicas
- ✅ Configured Nginx Ingress with host-based routing
- ✅ Implemented ConfigMaps and Secrets with volume mounts
- ✅ Set up Prometheus and Grafana monitoring stack
- ✅ Monitored live Kubernetes traffic with Kubeshark
- ✅ Built a personal portfolio page deployed on Kubernetes

---

## 🙏 Acknowledgements
Special thanks to:
- **Abhishek Veeramalla** for the amazing free DevOps courses
- **CNCF** for Kubernetes and Prometheus
- **Grafana Labs** for Grafana
- **Kubeshark** for network monitoring tools
## Author
**Mahesh Tirumalasetti**
- 📧 Email: tirumalasetti.usedu@gmail.com
