# Microservices Deployment with Kubernetes

## 📌 Project Title:
**Deploying and Managing Microservices in a Cloud-Native Environment**

## 🧑‍💻 Author:
**Nikhil Mandage**  
Cloud & DevOps Intern, Cravita Technologies

---

## 📖 Introduction

This project demonstrates the migration of a monolithic application to a microservices architecture using Docker and Kubernetes. It simulates a production-grade deployment pipeline with containerized Flask services orchestrated via Minikube, along with service discovery, autoscaling, and persistent storage.

---

## 🎯 Objectives

- Containerize and deploy microservices
- Set up and manage a Kubernetes cluster
- Enable service discovery, autoscaling, and persistent storage
- Create a production-like microservices deployment

---

## 🛠️ Technology Stack

- **Language**: Python (Flask)
- **Containerization**: Docker
- **Orchestration**: Kubernetes (Minikube)
- **Monitoring**: Metrics Server
- **Tools**: kubectl, Docker Hub, hey/curl

---

## ⚙️ System Architecture

End User / CLI
|
NodePort Service (Exposes Services)
|
| | |
User Service Product Service Order Service
| | |
| Horizontal Pod Autoscaler |
| |
| Persistent Volume & Claim

---

## 🧰 Requirements

### Software:
- Ubuntu OS
- Docker
- Kubernetes CLI (`kubectl`)
- Minikube

### Application Components:
- User Service (Flask)
- Product Service (Flask)
- Order Service (Flask)

---

## 🚀 Implementation Steps

1. **Microservices Development**  
   - Flask apps for User, Product, and Order services

2. **Dockerfile Creation**  
   - Used Python base image  
   - Installed dependencies & exposed ports

3. **Image Build & Push**  
   - Built images & pushed to Docker Hub

4. **Kubernetes Setup**  
   - Started Minikube and verified cluster

5. **Deployments**  
   - Created YAML files for Deployment and Services  
   - Deployed via `kubectl apply`

6. **Service Exposure**  
   - ClusterIP for internal access  
   - NodePort for external access

7. **Horizontal Pod Autoscaler (HPA)**  
   - Installed `metrics-server`  
   - Configured CPU-based HPA for Product Service  
   - Verified scaling with load generator (`hey`)

8. **Persistent Storage**  
   - Defined PersistentVolume and PersistentVolumeClaim  
   - Mounted to Order Service  
   - Verified persistence across pod restarts

---

## ✅ Results

- All services deployed and running in Kubernetes
- Product Service successfully auto-scaled with HPA
- Persistent volume retained Order Service data across restarts
- Microservices communicated as expected

---
## 📁 Directory Structure

.
├── user-service/
│ ├── app.py
│ └── Dockerfile
├── product-service/
│ ├── app.py
│ └── Dockerfile
├── order-service/
│ ├── app.py
│ └── Dockerfile
├── k8s-deployments/
│ ├── user-deployment.yaml
│ ├── product-deployment.yaml
│ ├── order-deployment.yaml
│ └── hpa.yaml
├── persistent-volume/
│ ├── pv.yaml
│ └── pvc.yaml

