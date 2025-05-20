# 🛍️ ABC Retail DevOps CI/CD Project

This project demonstrates the implementation of a full DevOps CI/CD pipeline for a sample retail application using Jenkins, Docker, Ansible, Kubernetes, Prometheus, and Grafana.

---

## 📌 Project Objective

ABC Technologies, a leading online retail store, is transitioning from traditional deployments to a modern DevOps-driven pipeline to solve issues around scalability, availability, performance, and time-to-market.

This project implements:
- Continuous Integration and Delivery with Jenkins
- Docker-based containerization
- Ansible for automation
- Kubernetes for deployment
- Prometheus + Node Exporter for monitoring
- Grafana for visualizing system metrics

---

## ⚙️ Tech Stack

| Tool          | Purpose                           |
|---------------|-----------------------------------|
| Java + Maven  | Build and manage dependencies     |
| GitHub        | Source code management            |
| Jenkins       | CI/CD orchestration               |
| Docker        | Containerization                  |
| Ansible       | Automation and provisioning       |
| Kubernetes    | Container orchestration           |
| Prometheus    | Monitoring                        |
| Grafana       | Visualization                     |

---

## 🚀 Pipeline Stages

1. **Code pushed to GitHub**
2. **Jenkins** pipeline:
   - Checkout → Build (Maven) → Dockerize WAR → Push Image
   - Trigger **Ansible Playbook** to run container
3. **Ansible** provisions the Docker container
4. **Kubernetes** (Minikube) deployment via manifests
5. **Prometheus** scrapes metrics (system + node_exporter)
6. **Grafana** displays metrics via dashboard panels

---

## 🧪 Project Structure

```
devOPS_Project1/
├── ansible/
│   └── run_docker.yml
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
├── src/
│   ├── main/
│   └── test/
├── Dockerfile
├── Jenkinsfile
├── pom.xml
├── prometheus.yml
├── grafana_dashboard.json
└── README.md
```

---

## 📈 Grafana Metrics

The following system metrics are monitored:
- ✅ CPU Usage (%)
- ✅ Memory Usage (%)
- ✅ Disk Space Available
- ✅ Network In/Out
- ✅ Load Average
- ✅ JVM Uptime
- ✅ Number of Running Docker Containers

---

## 🛠️ Setup Instructions (for Evaluator)

1. Clone the repository
2. Ensure Docker, Jenkins, Minikube, Prometheus, Grafana are installed
3. Import the `grafana_dashboard.json` into Grafana
4. Apply K8s manifests:
   ```bash
   kubectl apply -f k8s/deployment.yaml
   kubectl apply -f k8s/service.yaml
   ```
5. Open:
   - Prometheus: `http://localhost:9090`
   - Grafana: `http://localhost:3000` (admin/admin)
   - Retail App: `minikube service retail-service`

---

## ✅ Status

- [x] GitHub Setup
- [x] Jenkins Pipeline
- [x] Docker Integration
- [x] Ansible Automation
- [x] Kubernetes Deployment
- [x] Prometheus Monitoring
- [x] Grafana Dashboard

---

## 🧾 Author

**Vaibhav Oza**  
Post Graduate Certification Program in DevOps
