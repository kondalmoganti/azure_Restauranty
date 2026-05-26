Restauranty – Cloud Native DevOps Project

A production-style cloud-native microservices application deployed on Azure Kubernetes Service (AKS) with complete DevOps practices including:

Kubernetes orchestration
Docker containerization
GitHub Actions CI/CD
Azure Container Registry (ACR)
Monitoring with Prometheus & Grafana
HTTPS using cert-manager & Let’s Encrypt
Custom domain integration
Live Application
https://restauranty.kondal.online
Architecture Overview

The application follows a microservices-based architecture deployed on Azure AKS.

Components
Frontend
React.js application
Served through NGINX
Accessible via HTTPS
Backend Services
Auth Service
Items Service
Discounts Service
Database
MongoDB running inside Kubernetes
Infrastructure
Azure Kubernetes Service (AKS)
Azure Container Registry (ACR)
NGINX Ingress Controller
cert-manager
Prometheus & Grafana
Architecture Diagram

(Add your architecture image here)

![Architecture](./screenshots/architecture.png)
Tech Stack
Category	Technology
Cloud	Microsoft Azure
Containerization	Docker
Orchestration	Kubernetes (AKS)
CI/CD	GitHub Actions
Monitoring	Prometheus + Grafana
Ingress	NGINX Ingress Controller
SSL	cert-manager + Let’s Encrypt
Frontend	React.js
Backend	Node.js
Database	MongoDB
CI/CD Workflow

The CI/CD pipeline is implemented using GitHub Actions.

Workflow
Developer pushes code to GitHub
GitHub Actions pipeline starts
Docker images are built
Images pushed to Azure Container Registry
Kubernetes manifests deployed to AKS
Kubernetes Components
Namespace
kubectl get ns

Namespace used:

restauranty-km
Deployments
kubectl get deployments -n restauranty-km

Services deployed:

frontend
auth
items
discounts
mongo
Ingress

NGINX Ingress routes external traffic to services.

kubectl get ingress -n restauranty-km
Monitoring Stack

Monitoring stack deployed using:

helm install monitoring prometheus-community/kube-prometheus-stack
Components
Prometheus
Grafana
Alertmanager
Node Exporter
HTTPS & Security

HTTPS enabled using:

cert-manager
Let’s Encrypt

TLS certificates are automatically generated and renewed.

Secure URL
https://restauranty.kondal.online
Docker Images

Images stored in Azure Container Registry:

restaurantykm2468.azurecr.io
Project Structure
devops.restauranty/
├── backend/
│   ├── auth/
│   ├── discounts/
│   └── items/
├── client/
├── k8s/
├── .github/workflows/
└── README.md

Future Improvements
Horizontal Pod Autoscaler (HPA)
Persistent Volumes for MongoDB
ArgoCD GitOps deployment
Terraform Infrastructure as Code
Loki centralized logging
Blue/Green deployments
Key DevOps Concepts Demonstrated
Cloud-native architecture
Kubernetes orchestration
CI/CD automation
Containerized microservices
Monitoring & observability
HTTPS/TLS security
Azure cloud deployment
Author

Kondaiah Moganti

GitHub:

https://github.com/kondalmoganti
