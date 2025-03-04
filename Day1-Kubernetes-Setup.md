# Kubernetes Cluster Setup & Basics

## **1. Introduction**
Kubernetes is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications. This project focuses on setting up a Kubernetes cluster using **Minikube** for local development and exploring its core components.

## **2. Objectives**
- Install the required tools for Kubernetes setup.
- Set up a Kubernetes cluster using Minikube.
- Verify the cluster installation.
- Explore key Kubernetes components such as nodes, pods, services, and deployments.
- Access the Kubernetes dashboard for visualization.

## **3. Prerequisites**
Before proceeding with the setup, ensure that the following tools are installed:
- **kubectl**: Kubernetes command-line tool
- **Minikube**: A local Kubernetes environment
- **Virtualization support** (Docker, VirtualBox, or Hyper-V)

## **4. Installation & Setup**

### **Step 1: Install Kubectl**
Kubectl is the command-line tool used to interact with Kubernetes clusters.
```sh
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/
```
Verify installation:
```sh
kubectl version --client
```

### **Step 2: Install Minikube**
Minikube is used to run Kubernetes locally.
```sh
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```
Verify installation:
```sh
minikube version
```

### **Step 3: Start the Kubernetes Cluster**
Start the Minikube cluster with:
```sh
minikube start
```
Check Minikube status:
```sh
minikube status
```

### **Step 4: Verify the Cluster Installation**
Check cluster details:
```sh
kubectl cluster-info
```
List all nodes in the cluster:
```sh
kubectl get nodes
```
Expected output:
```
NAME       STATUS   ROLES                  AGE     VERSION
minikube   Ready    control-plane,master    2m      v1.25.0
```

## **5. Exploring Kubernetes Components**

### **Step 5: List Kubernetes Resources**
- List running pods:
  ```sh
  kubectl get pods --all-namespaces
  ```
- List available services:
  ```sh
  kubectl get services
  ```
- List deployments:
  ```sh
  kubectl get deployments
  ```

### **Step 6: Access Kubernetes Dashboard (Optional)**
Enable the Kubernetes dashboard:
```sh
minikube dashboard
```
This will open a web-based interface for managing the cluster.

## **6. Conclusion**
By following this project, we successfully set up a Kubernetes cluster using Minikube, explored its core components, and accessed the Kubernetes dashboard for monitoring. This provides a strong foundation for deploying and managing containerized applications in Kubernetes.

## **7. Future Scope**
- Deploy a sample application on Kubernetes.
- Configure networking and storage solutions.
- Implement Kubernetes monitoring tools like Prometheus and Grafana.




---------------------------------------------------------------------------------------------------------------------------------------------------------------------

# **Understanding the Errors and Fixes in Git and Minikube Setup**  

This document provides a detailed explanation of the errors encountered during your Git push and Minikube setup, explaining why they occurred, what they mean, and how to resolve them.

---

## **1. Git Push Error: `! [rejected] main -> main (fetch first)`**  
### **1.1 Why did this happen?**  
- Your local repository was out of sync with the remote repository.  
- Changes were made to the remote (`origin/main`) that you didn't have in your local branch (`main`).  
- Git prevents you from overwriting newer commits in the remote repository to avoid data loss.  

### **1.2 What does this error mean?**  
- Git is rejecting your push because your local repository is behind the remote repository.  
- You need to first pull the latest changes before pushing.  

### **1.3 How to fix it?**  
1️⃣ **Fetch and rebase remote changes** (recommended)  
```sh
git pull --rebase origin main
```
- This fetches the latest changes from the remote and re-applies your local changes on top of them.  

2️⃣ **Resolve conflicts (if any exist)**  
   - If Git asks you to resolve conflicts, manually fix them and then run:  
     ```sh
     git rebase --continue
     ```
   
3️⃣ **Push changes after syncing**  
   ```sh
   git push origin main
   ```
   - This successfully pushes your updated branch to the remote repository.

---

## **2. Minikube Start Error: `No possible driver was detected`**  
### **2.1 Why did this happen?**  
- Minikube requires a virtualization driver (Docker, VirtualBox, KVM, etc.) to create a local Kubernetes cluster.  
- Your system didn't have any of the required drivers installed.  

### **2.2 What does this error mean?**  
- Minikube couldn't find a compatible driver to start the cluster.  
- The error lists the missing drivers (`docker`, `kvm2`, `qemu2`, `podman`, `virtualbox`).  

### **2.3 How to fix it?**  
1️⃣ **Install Docker (recommended driver)**  
   ```sh
   sudo apt update
   sudo apt install -y docker.io
   ```
   
2️⃣ **Verify Docker installation**  
   ```sh
   docker --version
   ```
   
3️⃣ **Restart Minikube using Docker**  
   ```sh
   minikube start --driver=docker
   ```

---

## **3. Minikube Start Error: `The "docker" driver should not be used with root privileges`**  
### **3.1 Why did this happen?**  
- Minikube warns against running as `root` for security reasons.  
- Running Minikube as `root` can cause permission issues and security risks.  

### **3.2 What does this error mean?**  
- Minikube detected that you were using `sudo` (root) and prevented execution.  

### **3.3 How to fix it?**  
1️⃣ **Add your user to the Docker group (to avoid running as root)**  
   ```sh
   sudo usermod -aG docker $USER
   newgrp docker
   ```
   
2️⃣ **Try starting Minikube as a regular user**  
   ```sh
   minikube start --driver=docker
   ```

3️⃣ **If you still need to run as root (not recommended), force it**  
   ```sh
   minikube start --driver=docker --force
   ```
   - This bypasses the security warning but may lead to issues later.

---

## **Summary of Fixes**  
| **Error** | **Fix** |
|-----------|--------|
| `! [rejected] main -> main (fetch first)` | Run `git pull --rebase origin main`, resolve conflicts, then `git push` |
| `No possible driver was detected` | Install Docker (`sudo apt install docker.io`) and restart Minikube |
| `"docker" driver should not be used with root privileges` | Add your user to the Docker group and run without `sudo` |

These fixes should resolve the errors and allow you to continue working with Git and Minikube smoothly. 🚀 Let me know if you need further clarifications! 😊

