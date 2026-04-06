# ☸️ End-to-End Task Manager Deployment on Kubernetes (AWS EC2)

This project demonstrates a complete DevOps lifecycle: from containerizing a Python/Flask application to deploying it on a multi-node **Kubernetes Cluster** using **kubeadm** and **containerd** on **AWS EC2**.

---

## 🏗️ Architecture & Workflow
The application is deployed on a Kubernetes cluster consisting of a **Master Node** and a **Worker Node**.

1. **Dockerization:** Application is containerized using a Dockerfile.
2. **Registry:** Image is pushed to **Docker Hub** for centralized access.
3. **Infrastructure:** AWS EC2 instances are used for cluster nodes.
4. **Orchestration:** Kubernetes manages the deployment, scaling, and networking.



---

## 🛠️ Technologies Used
- **Cloud:** Amazon Web Services (AWS)
- **Containerization:** Docker
- **Orchestration:** Kubernetes (K8s)
- **Cluster Management:** Kubeadm
- **Container Runtime:** Containerd
- **Registry:** Docker Hub

---

## 🚀 Step-by-Step Implementation

### 1. Dockerizing & Pushing the Image
First, I built and tested the image locally before pushing it to the registry.

```bash
# Build the image
docker build -t mazidhossain/task-manager:latest .

# Test locally (Visit http://localhost:8080)
docker run -d -p 8080:80 --name task-manager-local mazidhossain/task-manager:latest

# Push to Docker Hub
docker login  # Use your Personal Access Token (PAT)
docker push mazidhossain/task-manager:latest
