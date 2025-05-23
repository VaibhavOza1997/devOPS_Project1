
# DevOps Project: CI/CD Pipeline for ABC Retail Application

**Participant:** Vaibhav Oza  
**Project Timeline:** April – May 2025  
**Tech Stack:** Jenkins, GitHub, Maven, Docker, Ansible, Kubernetes (Minikube), Prometheus, Grafana

---

## 🔧 1. Project Setup & Goals
- **Objective:** Build a complete DevOps pipeline from code push to deployment and monitoring.
- **Business Goal:** Transform a traditional retail app into a modern, CI/CD-enabled, highly available and scalable cloud-native application.
- **Initial Setup:**
  - Java, Maven, Git, Docker, Jenkins, Ansible installed on WSL2 Ubuntu (hosted on Windows).
  - Verified Java + Maven build for sample project (WAR packaging).

---

## 📁 2. GitHub Integration
- Project code pushed to GitHub: [`devOPS_Project1`](https://github.com/VaibhavOza1997/devOPS_Project1).
- Screenshots and documentation folders created for evidence and documentation.
- Readme and markdown explanation files generated.

---

## 🔄 3. CI/CD Pipeline with Jenkins
- Jenkins installed and configured on port `8080`.
- Created Jenkins Pipeline Job using `Jenkinsfile` to:
  1. Clone GitHub repo.
  2. Build WAR using Maven.
  3. Build Docker image (`abc-retail-app`).
  4. Trigger Ansible to run a playbook that launches Docker container.
- Pipeline execution verified with green build stages and console logs.

---

## 🐳 4. Docker Integration
- Dockerfile created to:
  - Use Tomcat 9 base image.
  - Copy WAR into `webapps/ROOT.war`.
- Docker image built and run locally:
  - `docker build -t abc-retail-app:latest .`
  - `docker run -d -p 9090:8080 --name retail-web abc-retail-app`
- Verified container from `docker ps` and app accessible via browser.

---

## 📦 5. Ansible Automation
- Wrote `run_docker.yml` playbook to run container automatically.
- Ansible integrated with Jenkins to run post-image build.
- Verified container launch using playbook.

---

## ☸️ 6. Kubernetes Deployment (Minikube)
- Minikube started using Docker driver.
- YAML files created and applied:
  - `deployment.yaml` (retail-app Deployment)
  - `service.yaml` (NodePort exposing app)
- App exposed and accessed via: `minikube service retail-service`

---

## 📈 7. Monitoring with Prometheus & Grafana
- Installed Prometheus (port `9091`) and Node Exporter (port `9100`).
- Configured `prometheus.yml` to scrape Node Exporter.
- Started Prometheus with `nohup` for persistence.
- Grafana installed and configured with Prometheus as data source.
- Dashboard imported with panels for:
  - CPU Usage (%)
  - Memory Usage (%)
  - Disk Available
  - Network In/Out
  - Load Average
- Panels verified and updated using Prometheus metrics.

---

## 📸 8. Documentation & Evidence
- All steps captured via screenshots and stored in GitHub folder.
- Markdown checklist + README created.
- Final structure includes:
  - `screenshots/`
  - `ansible/`
  - `k8s/`
  - `monitoring/`
  - `Dockerfile`, `Jenkinsfile`, `README.md`, `step_explanation.md`

---

## ✅ Final Outcome
- Fully functioning CI/CD pipeline with automation from GitHub to Kubernetes.
- System monitoring via Grafana with real-time metrics.
- Project aligned with business goals of scalability, speed, and automation.

