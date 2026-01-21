# 🚀 End-to-End CI/CD + GitOps Pipeline for Java Spring Boot Application

## 📌 Project Overview

This project demonstrates a **production-grade End-to-End CI/CD pipeline combined with GitOps principles** for a **Java Spring Boot application**.

The pipeline ensures that **every GitHub commit** is automatically:

* Built and tested
* Code-quality scanned
* Dockerized and pushed to Docker Hub
* Deployed to Kubernetes using **GitOps with Argo CD**

This architecture guarantees **consistent, repeatable, and automated deployments** using modern DevOps best practices.

---

## 🏗️ Architecture Overview

**CI (Continuous Integration)**
GitHub → Jenkins → SonarQube → Docker Hub

**CD (Continuous Deployment via GitOps)**
GitHub (K8s Manifests Repo) → Argo CD → Kubernetes Cluster

---

## 🧰 Tech Stack

| Category                | Tools / Technologies |
| ----------------------- | -------------------- |
| Language                | Java                 |
| Framework               | Spring Boot          |
| CI Tool                 | Jenkins              |
| Code Quality            | SonarQube            |
| Containerization        | Docker               |
| Image Registry          | Docker Hub           |
| Container Orchestration | Kubernetes           |
| GitOps CD               | Argo CD              |
| SCM                     | GitHub               |

---

## 🔄 CI/CD Workflow

### 1️⃣ Code Commit (GitHub)

* Developer pushes code to the GitHub repository
* Webhook triggers Jenkins pipeline automatically

### 2️⃣ Continuous Integration (Jenkins)

Jenkins performs the following stages:

1. **Checkout Source Code**
2. **Build Application** (Maven/Gradle)
3. **Run Unit Tests**
4. **Static Code Analysis** using SonarQube
5. **Docker Image Build**
6. **Push Image to Docker Hub**

Each build is tagged uniquely to maintain traceability.

### 3️⃣ GitOps Deployment (Argo CD)

* Jenkins updates Kubernetes manifest files with the new Docker image tag
* Changes are pushed to the **GitOps repository**
* Argo CD detects changes and syncs them to the Kubernetes cluster
* Application is deployed automatically without manual intervention

---

## 📂 Repository Structure

```
├── spring-boot-app/
│   ├── src/
│   ├── Dockerfile
│   ├── pom.xml
│
├── jenkins/
│   ├── Jenkinsfile
│
├── k8s-manifests/
│   ├── deployment.yaml
│   ├── service.yaml
│
├── README.md
```

---

## 🧪 Quality & Security

* **SonarQube** ensures:

  * Code smells detection
  * Bug analysis
  * Maintainability and reliability checks
* Pipeline fails automatically if quality gates are not met

---

## 🚀 Key Features

✅ Fully automated CI/CD pipeline
✅ GitOps-based Kubernetes deployment
✅ Zero manual deployment steps
✅ Rollback-friendly and version-controlled releases
✅ Scalable and production-ready architecture

---

## 📈 Benefits of Jenkins + Argo CD

| Jenkins (CI)    | Argo CD (CD)                  |
| --------------- | ----------------------------- |
| Build & Test    | Declarative Deployment        |
| Code Scanning   | Git as Single Source of Truth |
| Image Creation  | Auto Sync & Rollbacks         |
| Faster Feedback | Kubernetes Native             |

---

## 🛠️ Prerequisites

* Java 17+
* Docker
* Kubernetes Cluster (EKS / Minikube / Kind)
* Jenkins Server
* SonarQube Server
* Argo CD Installed on Kubernetes
* Docker Hub Account

---

## 📌 How to Run

1. Clone the repository
2. Configure Jenkins credentials (GitHub, Docker Hub, SonarQube)
3. Create Jenkins pipeline using `Jenkinsfile`
4. Install Argo CD on Kubernetes
5. Connect GitOps repository to Argo CD
6. Push code and watch the pipeline run 🚀

---

## 👨‍💻 Author

**Mayank Kaneriya**
DevOps | Cloud | Backend Engineer

---

## ⭐ Conclusion

This project showcases a **real-world DevOps CI/CD + GitOps implementation** used in modern cloud-native organizations, combining **Jenkins for CI** and **Argo CD for declarative CD** to achieve fast, reliable, and scalable deployments.

⭐ Star this repository if you found it useful!
