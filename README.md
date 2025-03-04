# 30-Day-Kubernetes-Challenge-for-Intermediate-Learners
Each day presents a hands-on project that builds on previous concepts, progressively deepening your Kubernetes expertise. Ensure you have access to a Kubernetes cluster (Minikube, Kind, or a cloud provider like AWS EKS, GKE, or AKS).


### **30-Day Kubernetes Challenge for Intermediate Learners**  
Each day presents a hands-on project that builds on previous concepts, progressively deepening your Kubernetes expertise. Ensure you have access to a Kubernetes cluster (Minikube, Kind, or a cloud provider like AWS EKS, GKE, or AKS).

---

## **Week 1: Core Kubernetes Concepts & Workloads**  

### **Day 1: Setup & Cluster Basics**  
- Set up a Kubernetes cluster using Minikube or a cloud provider.  
- Verify installation and explore cluster components (`kubectl cluster-info`, `kubectl get nodes`).  

### **Day 2: Creating and Managing Pods**  
- Deploy a basic Pod using a YAML manifest.  
- Experiment with `kubectl` commands to inspect logs, exec into containers, and delete Pods.  

### **Day 3: Deployments & Scaling**  
- Create a Deployment for a simple web application (e.g., Nginx).  
- Scale it up and down using `kubectl scale` and test rolling updates.  

### **Day 4: Services & Networking**  
- Expose your Deployment using a ClusterIP and NodePort Service.  
- Test service connectivity using `curl` from another Pod.  

### **Day 5: ConfigMaps & Secrets**  
- Store environment variables using ConfigMaps and Secrets.  
- Inject them into a Deployment and verify their usage inside the container.  

### **Day 6: Persistent Storage with PVCs**  
- Mount a Persistent Volume (PV) and Persistent Volume Claim (PVC) to a Pod.  
- Deploy a database (e.g., MySQL or PostgreSQL) with persistent storage.  

### **Day 7: Health Checks & Probes**  
- Implement readiness and liveness probes in a containerized application.  
- Observe how Kubernetes restarts unhealthy containers.  

---

## **Week 2: Intermediate Kubernetes Workloads & Ingress**  

### **Day 8: Multi-container Pods & Sidecars**  
- Deploy a Pod with a main app and a sidecar container for logging.  
- Share logs between containers using a shared volume.  

### **Day 9: Job & CronJob for Scheduled Tasks**  
- Create a Job that runs a script once and exits.  
- Schedule a CronJob to run a periodic task (e.g., a database backup).  

### **Day 10: Ingress Controllers & Routing**  
- Deploy an Nginx Ingress Controller.  
- Configure an Ingress resource to expose a web application via a custom domain.  

### **Day 11: TLS & HTTPS with Let's Encrypt**  
- Set up TLS termination using Cert-Manager and Let's Encrypt.  
- Secure an Ingress route with an SSL certificate.  

### **Day 12: Role-Based Access Control (RBAC)**  
- Create a ServiceAccount and bind it to a Role with limited permissions.  
- Test access control by restricting `kubectl` actions for a user.  

### **Day 13: Resource Requests & Limits**  
- Define CPU and memory limits for a Pod.  
- Monitor Pod behavior under different resource constraints.  

### **Day 14: Horizontal Pod Autoscaler (HPA)**  
- Configure HPA to scale a Deployment based on CPU utilization.  
- Simulate high traffic and observe auto-scaling in action.  

---

## **Week 3: Advanced Concepts & Helm**  

### **Day 15: StatefulSets for Stateful Applications**  
- Deploy a StatefulSet for a database (e.g., MongoDB or Redis).  
- Test data persistence across Pod restarts.  

### **Day 16: Headless Services & Service Discovery**  
- Use a Headless Service for inter-Pod communication.  
- Deploy multiple instances of an app and resolve their hostnames.  

### **Day 17: Custom Resource Definitions (CRDs)**  
- Create a simple CRD and define a custom Kubernetes resource.  
- Interact with it using `kubectl get <resource>`.  

### **Day 18: Helm - Package Management for Kubernetes**  
- Install Helm and deploy an application using a Helm chart.  
- Explore Helm values and upgrade an application.  

### **Day 19: Writing a Custom Helm Chart**  
- Create and package a Helm chart for a web application.  
- Publish it to a Helm repository.  

### **Day 20: Network Policies & Security**  
- Implement a NetworkPolicy to restrict traffic between namespaces.  
- Test connectivity using `netcat` or `curl`.  

### **Day 21: Logging & Fluentd/Elasticsearch/Kibana (EFK)**  
- Deploy the EFK stack for centralized logging.  
- Forward logs from an application to Elasticsearch.  

---

## **Week 4: Observability, CI/CD, and Production Readiness**  

### **Day 22: Prometheus for Metrics Collection**  
- Deploy Prometheus and configure it to scrape metrics from a running application.  
- Create a basic alerting rule.  

### **Day 23: Grafana Dashboards**  
- Visualize Kubernetes metrics using Grafana dashboards.  
- Create a custom dashboard for Pod CPU/memory usage.  

### **Day 24: Kubernetes Event-Driven Autoscaling (KEDA)**  
- Install KEDA and set up event-driven autoscaling based on a queue length metric.  

### **Day 25: CI/CD with ArgoCD**  
- Install ArgoCD and deploy an application via GitOps.  
- Modify the Git repo and observe ArgoCD’s automatic deployment.  

### **Day 26: Chaos Engineering with LitmusChaos**  
- Deploy LitmusChaos and introduce a fault (e.g., kill a Pod randomly).  
- Observe how Kubernetes handles failures.  

### **Day 27: Backup & Disaster Recovery with Velero**  
- Install Velero and back up application state.  
- Restore a deleted namespace from a backup.  

### **Day 28: Kubernetes Policy Enforcement with OPA/Gatekeeper**  
- Define a policy to enforce best practices (e.g., prevent Privileged Pods).  
- Test policy violations and enforcement.  

### **Day 29: Multi-cluster Management with Kubernetes Federation**  
- Set up a Kubernetes Federation control plane.  
- Deploy an application across multiple clusters.  

### **Day 30: Final Project - Deploy a Full-Stack Microservices App**  
- Deploy a complete microservices-based application (e.g., frontend, backend, database).  
- Implement Ingress, autoscaling, logging, and monitoring.  

---

## **Bonus Tips & Tools**  
- **kubectl plugins:** Use `kubectl-neat`, `kubectl-tree`, `kubectx` for efficiency.  
- **K9s:** A terminal UI for managing Kubernetes clusters.  
- **Lens:** A powerful Kubernetes dashboard.  
- **Kind:** For running Kubernetes clusters locally using Docker.  

By the end of this challenge, you'll have hands-on experience with real-world Kubernetes scenarios, making you more confident in deploying, scaling, and managing containerized applications. 🚀
