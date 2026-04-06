# ☸️ Task Manager Deployment on Kubernetes (AWS EC2)

A hands-on DevOps project demonstrating the deployment of a containerized application on a Kubernetes cluster using **kubeadm**, **containerd**, and **AWS**.

## 🛠 Tech Stack
- **Infrastructure:** AWS EC2 (Master & Worker Nodes)
- **Containerization:** Docker & Docker Hub
- **Orchestration:** Kubernetes (v1.28+)
- **Runtime:** Containerd

## 🚀 Quick Start
1. **Build & Push:**
   `docker build -t mazidhossain/task-manager:latest .`
   `docker push mazidhossain/task-manager:latest`

2. **Cluster Setup:** Bootstrapped using `kubeadm init` and joined worker nodes. Used Calico for Pod networking.

3. **Deploy:**
   `kubectl apply -f deployment.yaml`
   `kubectl apply -f service.yaml`

## 📂 Key Manifests
### Deployment
- Replicas: 2 (High Availability)
- Image: `mazidhossain/task-manager:latest`

### Service (NodePort)
- Port: 80 | TargetPort: 80 | NodePort: 30080

## 🔍 Result
The application is accessible at: `http://<Worker-Node-IP>:30080`
Verify with: `kubectl get all -n kubernetes-cluster`
