# CICD-PIPELINE — DevOps Project

A complete end-to-end DevOps pipeline built for learning and practice.  
Covers the full lifecycle: **Source → Build → Code Quality → Docker → Kubernetes → Monitoring**

>  Learned from and built following the guidance of **Abhishek Veeramalla**

 
##  Project Overview

This project demonstrates a real-world CI/CD pipeline setup .
The goal was to understand each DevOps tool individually and wire them together into a working pipeline.


## Tech Stack

| Tool           | Purpose                                              |
|------          |---------                                             |
| **GitHub**     | Source code management & SCM trigger                 |
| **Jenkins**    | CI/CD automation & pipeline orchestration            |
| **Maven**      | Java project build tool                              |
| **SonarQube**  | Static code analysis & quality gate                  |
| **Docker**     | Containerization of the application                  |
| **Kubernetes** | Container orchestration & deployment                 |
| **Prometheus** | Metrics collection & alerting                        |
| **Grafana**    | Monitoring dashboards & visualization                |
| **ngrok**      | Exposing local Jenkins to the internet (for webhooks)|


##  Pipeline Stages

GitHub Push
    │
    ▼
Jenkins (Triggered via Webhook)
    │
    ├── Stage 1: SCM Checkout
    │       └── Pull latest code from GitHub
    │
    ├── Stage 2: Build
    │       └── mvn clean package (Maven)
    │
    ├── Stage 3: SonarQube Analysis
    │       └── Code quality scan & report
    │
    ├── Stage 4: Docker Build
    │       └── Build image from Dockerfile
    │
    └── Stage 5: Deploy to Kubernetes
            └── kubectl apply deployment.yaml + service.yaml


## 📁 Project Structure

CICD-PIPELINE/
├── Jenkinsfile              # Declarative Jenkins pipeline
├── Dockerfile               # Docker image using nginx
├── deployment.yaml          # Kubernetes Deployment manifest
├── service.yaml             # Kubernetes Service (NodePort)
├── sonar-project.properties # SonarQube scanner config
├── pom.xml                  # Maven build config with Sonar plugin
├── index.html               # Static web page served via nginx
└── prometheus.yml           # Prometheus scrape config



## 📝 What I Learned

- Setting up Jenkins from scratch and writing declarative pipelines
- Integrating SonarQube with Jenkins for automated code quality checks
- Building and running Docker containers
- Writing Kubernetes `deployment.yaml` and `service.yaml` manifests
- Connecting Prometheus with node_exporter and visualizing data in Grafana
- Using ngrok to expose local services for GitHub webhooks


##  Author

**Khushi Mangal**  
GitHub: [@khushimangal770-oss](https://github.com/khushimangal770-oss)
