# Project Steps & Documentation

## 1. Source Code Upload
- Source code pushed to GitHub in structured folders.
- Maven project with `src`, `target`, and `pom.xml`.

## 2. Jenkins CI Pipeline
- Jenkins jobs created for Build, Test, and Package phases.
- WAR file generated and archived.

## 3. Docker Image Creation
- Dockerfile used to containerize the application.
- Jenkins integrated to build Docker image and tag it `abc-retail-app:latest`.

## 4. Ansible Automation
- Ansible playbook used to run Docker container from the image.
- Integrated as part of Jenkins pipeline.

## 5. Kubernetes Deployment
- YAML files created for Deployment and Service.
- Image deployed on local Kubernetes (Minikube).
- Application accessed at `localhost:9090`.

## 6. Prometheus Monitoring
- Prometheus installed and configured to scrape metrics from `node_exporter`.

## 7. Grafana Dashboard
- Dashboard created to monitor:
  - CPU Usage
  - Memory Usage
  - Disk Space
  - Network In/Out
  - Load Average
- Dashboard imported using JSON and Prometheus as data source.

## 8. GitHub Structure
- README.md created
- All YAML, Docker, Jenkins, and Ansible files committed.
- Screenshots uploaded to `/docs` folder.
