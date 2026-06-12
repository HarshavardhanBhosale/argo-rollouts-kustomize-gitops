# Argo Rollouts Canary Deployment using Kustomize

## Overview

This project demonstrates a production-style Canary Deployment strategy on Kubernetes using **Argo Rollouts**, **Kustomize**, and **NGINX Ingress Controller**. The implementation enables progressive traffic shifting between application versions, reducing deployment risks and ensuring zero-downtime releases.

The project follows GitOps principles by managing Kubernetes manifests through Kustomize overlays, making deployments reusable, maintainable, and environment-specific.

---
## Architecture Demo

![Architecture Demo](./Screenshots/modern-argo-rollouts-animation(1).gif)

modern-argo-rollouts-animation(1).gif
---
## Key Features

* Canary Deployments with Argo Rollouts
* Progressive Traffic Shifting
* Zero-Downtime Releases
* Kubernetes Native Deployment Strategy
* Kustomize-Based Configuration Management
* NGINX Ingress Integration
* GitOps-Friendly Structure
* Automated Rollout Promotion Workflow

---

## Tech Stack

* Kubernetes
* Argo Rollouts
* Kustomize
* Docker
* NGINX Ingress Controller
* YAML

---

## Project Architecture

```text
User Traffic
      │
      ▼
NGINX Ingress Controller
      │
      ▼
Argo Rollouts
      │
 ┌────┴────┐
 │         │
 ▼         ▼
Stable   Canary
Version  Version
```

---

## Repository Structure

```text
.
├── base/
│   ├── deployment.yaml
│   ├── service.yaml
│   └── kustomization.yaml
│
├── prod/
│   ├── rollout.yaml
│   ├── ingress.yaml
│   ├── service.yaml
│   ├── preview-service.yaml
│   └── kustomization.yaml
│
└── screenshots/
```

---

## Canary Rollout Strategy

The deployment gradually shifts production traffic to the new version using weighted routing:

| Stage  | Traffic Shift |
| ------ | ------------- |
| Step 1 | 20%           |
| Step 2 | 40%           |
| Step 3 | 60%           |
| Step 4 | 80%           |
| Step 5 | 100%          |

Each stage can be validated before proceeding to the next phase, minimizing deployment risk.

---

## Implementation Highlights

### Argo Rollouts

Configured a Kubernetes Rollout resource to manage application updates using the Canary strategy instead of the default Deployment controller.

### Kustomize

Organized manifests into reusable base configurations and environment-specific overlays for easier management and scalability.

### Traffic Management

Integrated NGINX Ingress Controller with Argo Rollouts to dynamically split traffic between stable and canary versions during deployments.

---

## Results

* Successfully deployed application using Argo Rollouts
* Verified progressive traffic shifting between versions
* Achieved zero-downtime deployment process
* Implemented GitOps-ready Kubernetes manifest structure
* Demonstrated production-grade release strategy
  
---

## Skills Demonstrated

* Kubernetes Administration
* Argo Rollouts
* Canary Deployments
* GitOps Practices
* Kustomize
* Kubernetes Networking
* NGINX Ingress
* Deployment Automation

---

## Author

### Harshavardhan Bhosale

DevOps & Cloud Engineer

**Areas of Interest**

* Kubernetes
* DevOps
* GitOps
* Cloud Infrastructure
* CI/CD Automation

---

## License

This project is available for learning, demonstration, and portfolio purposes.

---

![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![Argo Rollouts](https://img.shields.io/badge/Argo%20Rollouts-EF7B4D?style=for-the-badge)
![Kustomize](https://img.shields.io/badge/Kustomize-000000?style=for-the-badge)
![NGINX](https://img.shields.io/badge/NGINX-009639?style=for-the-badge&logo=nginx&logoColor=white)

