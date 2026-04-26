# 🚀 Super Mario DevSecOps Project

![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)

This project demonstrates the implementation of a full Software Development Life Cycle (**SDLC**) using modern **DevSecOps** practices. We deployed the classic Super Mario game on a Kubernetes cluster, automating security, monitoring, and continuous deployment.

## 🏗️ System Architecture

The project is built on four core pillars:

1.  **Orchestration:** Deployed on **Kubernetes (K3d)** using Deployments, Services, and Persistent Volume Claims (**PVC**) for state management.
2.  **CI/CD Pipeline:** Fully automated via **GitHub Actions** for building and pushing images to Docker Hub.
3.  **Security (SecOps):** * Static Image Analysis with **Trivy** (Vulnerability Scanning).
    * **Network Policies** to ensure traffic isolation.
    * Role-Based Access Control (**RBAC**) implementation.
4.  **Observability:** Monitoring stack using **Prometheus** for metrics collection and **Grafana** for real-time resource visualization.

## 🛠️ Tech Stack

* **Infrastructure:** K3d (Lightweight Kubernetes).
* **Containerization:** Docker & Docker Hub.
* **CI/CD:** GitHub Actions.
* **Security:** Aquasecurity Trivy.
* **Monitoring:** Prometheus Stack (Helm Charts).

## 🚀 CI/CD Pipeline

The workflow triggers automatically on every `push` to the `main` branch:
1.  **Checkout:** Pulls the latest source code.
2.  **Docker Login:** Secure authentication using GitHub Secrets.
3.  **Build & Push:** Builds an optimized Docker image and pushes it to Docker Hub.
4.  **Security Scan:** Scans for "Critical" and "High" vulnerabilities. If the risk exceeds the threshold, the pipeline fails to protect the production environment.

## 📈 Monitoring & Insights

Grafana dashboards were implemented to track:
* CPU and Memory consumption per Pod.
* Cluster Node health status.
* Network metrics for the Mario deployment.

---

## 🔧 Installation & Deployment

### Prerequisites:
* Docker installed.
* K3d & Kubectl installed.

### Steps:
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/marioscloud/mario-kubernetes-project1.git](https://github.com/marioscloud/mario-kubernetes-project1.git)
    cd mario-kubernetes-project1
    ```
2.  **Create the cluster:**
    ```bash
    k3d cluster create mario-cluster -p "8080:80@loadbalancer"
    ```
3.  **Apply manifests:**
    ```bash
    kubectl apply -f .
    ```

---
**Developed by [Your Name / MariosCloud]** *DevSecOps Engineer in training | Passionate about Infrastructure as Code (IaC) and Automation.*

---
**Developed by Mario Araos ** *Devops Engineer| Pasion for infrastructure and automation |LFCS | CKA*
