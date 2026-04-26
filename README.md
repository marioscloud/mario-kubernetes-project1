# 🚀 Super Mario DevSecOps Project

![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)

Este proyecto demuestra la implementación de un ciclo de vida completo de software (**SDLC**) utilizando prácticas modernas de **DevSecOps**. Desplegamos el clásico juego de Super Mario sobre un clúster de Kubernetes, automatizando la seguridad, el monitoreo y el despliegue continuo.

## 🏗️ Arquitectura del Sistema

El proyecto se basa en cuatro pilares fundamentales:

1.  **Orquestación:** Despliegue en **Kubernetes (K3d)** utilizando Deployments, Services y gestión de volúmenes persistentes (**PVC**).
2.  **Pipeline CI/CD:** Automatización total mediante **GitHub Actions** para el build y push de imágenes a Docker Hub.
3.  **Seguridad (SecOps):** * Análisis estático de imágenes con **Trivy** (Vulnerability Scanning).
    * Políticas de red (**Network Policies**) para aislar el tráfico.
    * Control de acceso basado en roles (**RBAC**).
4.  **Observabilidad:** Stack de monitoreo con **Prometheus** para la recolección de métricas y **Grafana** para la visualización de recursos en tiempo real.

## 🛠️ Tecnologías Utilizadas

* **Infraestructura:** K3d (Lightweight Kubernetes).
* **Contenedores:** Docker & Docker Hub.
* **CI/CD:** GitHub Actions.
* **Seguridad:** Aquasecurity Trivy.
* **Monitoreo:** Prometheus Stack (Helm Chart).

## 🚀 Pipeline de CI/CD

El flujo de trabajo se dispara automáticamente con cada `push` a la rama `main`:
1.  **Checkout:** Descarga del código fuente.
2.  **Docker Login:** Autenticación segura mediante GitHub Secrets.
3.  **Build & Push:** Construcción de la imagen optimizada y envío a Docker Hub.
4.  **Security Scan:** Escaneo de vulnerabilidades críticas y altas. Si el riesgo es inaceptable, el pipeline falla protegiendo el entorno.

## 📈 Monitoreo y Resultados

Se implementaron dashboards en Grafana para supervisar:
* Consumo de CPU y Memoria por Pod.
* Estado de salud de los nodos del clúster.
* Métricas de red del despliegue de Mario.

---

## 🔧 Instalación y Despliegue Local

### Pre-requisitos:
* Docker instalado.
* K3d & Kubectl.

### Pasos:
1.  **Clonar el repositorio:**
    ```bash
    git clone https://github.com/marioscloud/mario-kubernetes-project1.git
    cd mario-kubernetes-project1
    ```
2.  **Crear el clúster:**
    ```bash
    k3d cluster create mario-cluster -p "8080:80@loadbalancer"
    ```
3.  **Aplicar manifiestos:**
    ```bash
    kubectl apply -f .
    ```

---
**Developed by Mario Araos *Devops Engineer | Pasion for infrastructure and automation | LFCS | CKA *
