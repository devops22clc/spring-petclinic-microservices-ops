# Spring Petclinic Microservices - Ops

This repository contains the infrastructure and DevOps configurations to deploy and manage the [Spring Petclinic Microservices](https://github.com/devops22clc/spring-petclinic-microservices) application using Jenkins CI/CD pipelines and Kubernetes.

## 🚀 Overview

The Petclinic system is a sample application built using Spring Boot and Microservices architecture. This repo focuses on:

- Setting up Jenkins pipelines for CI/CD
- Building and pushing Docker images
- Deploying services to a Kubernetes cluster
- Managing multiple environments (development and staging)
- Supporting dynamic branch-based deployments for developers

---

## 🛠️ Technologies Used

- **Jenkins** – CI/CD automation
- **Kubernetes (Minikube / Cluster)** – Container orchestration
- **Docker** – Containerization
- **Helm** – Kubernetes package manager
- **Git & GitHub** – Version control
- **Spring Boot** – Java-based microservices
---

## 🔧 Features

- **CI Pipelines**
  - Triggered on every code push to any branch
  - Builds Docker images with commit-specific tags
  - Pushes images to Docker Hub

- **CD Pipelines**
  - Jenkins Job `developer_build` allows branch-specific deployment
  - Supports dynamic deployment with parameters (e.g., deploy `dev_vets_service` branch while keeping others on `main`)
  - Deploys to Kubernetes with NodePort exposure for direct testing

- **Multi-Environment Deployment**
  - `main` branch changes auto-deploy to `dev` namespace
  - Git tags like `v1.2.3` trigger deploy to `staging` namespace

- **Clean-Up Jobs**
  - Jenkins job to remove previously deployed environments for a developer

---

## 📦 Folder Structure

```bash
spring-petclinic-microservices-ops/      # K8s manifests cho từng môi trường ổn định
├── spring-petclinic-admin-server/       # K8s manifests cho Admin Server
├── spring-petclinic-api-gateway/        # K8s manifests cho API Gateway
├── spring-petclinic-config-server/      # K8s manifests cho Config Server
├── spring-petclinic-customers-service/  # K8s manifests cho Customers Service
├── spring-petclinic-discovery-server/   # K8s manifests cho Discovery Server
├── spring-petclinic-genai-service/      # K8s manifests cho GenAI Service
├── spring-petclinic-vets-service/       # K8s manifests cho Vets Service
├── spring-petclinic-visits-service/     # K8s manifests cho Visits Service
├── argocd/                              # Cấu hình ArgoCD để triển khai GitOps
├── README.md                        

