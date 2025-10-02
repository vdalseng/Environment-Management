# Continuous Deployment
## Technologies Overview

This pipeline uses a modern, free toolchain for building, testing, deploying, and monitoring applications. Tools are grouped and ordered by setup sequence, with concise descriptions for each.


### 1. Local Kubernetes Cluster
**kind**: Runs a local Kubernetes cluster in Docker containers for realistic, production-like testing.  
[Download kind](https://kind.sigs.k8s.io/docs/user/quick-start/)


### 2. Application Packaging
**Docker**: Build and package applications into containers for consistent deployment across environments.  
[Download Docker](https://docs.docker.com/get-docker/)

**Podman**: Alternative to Docker for containerization.  
[Download Podman](https://podman.io/getting-started/installation)


### 3. Infrastructure as Code
**Terraform**: Define and provision infrastructure using code for repeatable, automated setups.  
[Download Terraform](https://developer.hashicorp.com/terraform/downloads)


### 4. CI/CD Automation
**GitHub Actions**: Automate build, test, and deployment workflows. Integrates with Docker, Terraform, and Kubernetes.  
[Learn about GitHub Actions](https://docs.github.com/en/actions)


### 5. Kubernetes Deployment & Rollouts
**Helm**: Package and manage Kubernetes applications with versioning and easy rollbacks.  
[Download Helm](https://helm.sh/docs/intro/install/)

**ArgoCD**: GitOps tool for syncing application state from Git to Kubernetes, handling deployments and rollbacks.  
[Download ArgoCD](https://argo-cd.readthedocs.io/en/stable/getting_started/)

**Argo Rollouts**: Advanced deployment strategies (canary, blue-green) for zero-downtime updates. Integrates with ArgoCD and Helm.  
[Download Argo Rollouts](https://argoproj.github.io/argo-rollouts/installation/)


### 6. Secrets Management
**Kubernetes Secrets**: Store and manage sensitive data natively in Kubernetes. Simple, free, and CI/CD friendly.  
[Kubernetes Secrets documentation](https://kubernetes.io/docs/concepts/configuration/secret/)


### 7. Monitoring
**Prometheus**: Collect metrics and monitor application and cluster health.  
[Download Prometheus](https://prometheus.io/download/)

**Grafana**: Visualize metrics and create dashboards for real-time monitoring and alerting.  
[Download Grafana](https://grafana.com/get/)

---

**Setup Order:**
1. kind
2. Docker / Podman
3. Terraform
4. GitHub Actions
5. Helm
6. ArgoCD + Argo Rollouts
7. Kubernetes Secrets
8. Prometheus & Grafana