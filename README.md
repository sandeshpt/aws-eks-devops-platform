# AWS EKS DevOps Platform

A production-style DevOps learning project for building, deploying, automating, and operating a containerized application on Amazon EKS.

The project is designed to demonstrate practical experience across AWS, Kubernetes, Terraform, Jenkins, Docker, Helm, Python automation, Linux, Ansible, CI/CD, monitoring, and SRE troubleshooting.

## Project Goals

- Provision AWS infrastructure using Terraform and Infrastructure as Code practices.
- Containerize a Python REST API using Docker.
- Store container images in Amazon ECR.
- Deploy and operate workloads on Amazon EKS.
- Package Kubernetes resources using Helm.
- Build an automated CI/CD pipeline using Jenkins.
- Use Python and Bash for operational automation.
- Use Ansible where configuration management is appropriate.
- Implement health checks, scaling, monitoring, and observability.
- Practice production troubleshooting and rollback scenarios.

## Planned Architecture

```text
Developer
   |
   v
GitHub
   |
   v
Jenkins CI/CD
   |
   +--> Test
   +--> Docker Build
   +--> Push Image to Amazon ECR
   |
   v
Amazon EKS
   |
   +--> Helm Deployment
   +--> Kubernetes Service
   +--> Ingress / AWS Load Balancer
   |
   v
Python Application
   |
   v
Amazon RDS

Infrastructure: Terraform -> VPC / IAM / ECR / EKS / RDS
Monitoring: CloudWatch + Prometheus + Grafana
Automation: Python + Bash + Ansible
```

## Technology Stack

| Area | Technologies |
| --- | --- |
| Cloud | AWS |
| Containers | Docker |
| Orchestration | Kubernetes, Amazon EKS |
| Infrastructure as Code | Terraform |
| CI/CD | Jenkins, GitHub |
| Packaging | Helm |
| Application | Python, Flask |
| Automation | Python, Bash, Ansible |
| Registry | Amazon ECR |
| Database | Amazon RDS |
| Monitoring | Amazon CloudWatch, Prometheus, Grafana |
| Operating System | Linux |

## Repository Structure

```text
aws-eks-devops-platform/
|
+-- application/
|   +-- app.py
|   +-- requirements.txt
|   +-- tests/
|       +-- test_app.py
|
+-- docker/                 # Planned
+-- terraform/              # Planned
+-- kubernetes/             # Planned
+-- helm/                   # Planned
+-- ansible/                # Planned
+-- jenkins/                # Planned
+-- scripts/                # Planned
+-- monitoring/             # Planned
+-- docs/                   # Planned
+-- README.md
```

## Phase 1 - Python REST API

The first phase contains a lightweight Flask API that will later be containerized and deployed to EKS.

### API Endpoints

| Endpoint | Purpose |
| --- | --- |
| `/` | Application endpoint |
| `/health` | Health/liveness endpoint |
| `/ready` | Readiness endpoint |

The `/health` and `/ready` endpoints will later be integrated with Kubernetes liveness and readiness probes.

### Run Locally

```bash
git clone https://github.com/sandeshpt/aws-eks-devops-platform.git
cd aws-eks-devops-platform/application
python -m venv venv
```

Windows:

```bash
venv\Scripts\activate
```

Linux/macOS:

```bash
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Start the application:

```bash
python app.py
```

Test the endpoints at:

```text
http://localhost:5000/
http://localhost:5000/health
http://localhost:5000/ready
```

Run automated tests:

```bash
pytest -v
```

## Project Roadmap

- [x] Create GitHub repository
- [x] Build initial Python Flask REST API
- [x] Add health and readiness endpoints
- [x] Add automated Python tests
- [ ] Containerize application with Docker
- [ ] Create AWS infrastructure with Terraform
- [ ] Configure Amazon ECR
- [ ] Provision Amazon EKS
- [ ] Deploy Kubernetes workloads
- [ ] Package deployment using Helm
- [ ] Build Jenkins CI/CD pipeline
- [ ] Add Python and Bash operational automation
- [ ] Add Ansible configuration management
- [ ] Configure CloudWatch monitoring
- [ ] Deploy Prometheus and Grafana
- [ ] Configure HPA, probes, resource limits, and resilience controls
- [ ] Implement deployment validation and rollback
- [ ] Practice production incident and troubleshooting scenarios

## Production Scenarios Covered

As the project progresses, it will include practical troubleshooting exercises for issues such as `CrashLoopBackOff`, `ImagePullBackOff`, Pending pods, `OOMKilled`, failed health probes, Kubernetes DNS problems, IAM permission failures, RDS connectivity problems, HTTP 502/503/504 errors, Jenkins deployment failures, Terraform drift/state issues, and failed Kubernetes rollouts.

## Current Status

**Phase 1: Python REST API - In Progress**

Next milestone: run and test the application locally, then containerize it using Docker.

---

Built as a hands-on DevOps engineering and production troubleshooting project.
