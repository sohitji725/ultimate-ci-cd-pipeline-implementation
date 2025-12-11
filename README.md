# Jenkins Pipeline for Java based application using Maven, SonarQube, Argo CD, Helm and Kubernetes

![CI/CD Pipeline](https://user-images.githubusercontent.com/43399466/228301952-abc02ca2-9942-4a67-8293-f76647b6f9d8.png)

# 🚀 Production-Grade CI/CD Pipeline with Jenkins, Docker, SonarQube, Argo CD & Kubernetes

### 🧩 The Problem  
Manual deployments often cause:
- Slow release cycles  
- Increased bugs  
- Unpredictable deployments  
- High operational stress  

### ✅ The Solution  
A fully automated, end-to-end CI/CD pipeline that:
- Reduces deployment time from **hours to minutes**
- Ensures high code quality and security
- Enables **GitOps** and **safe automated rollouts**

---

## 🎯 Key Features
- **Automated Quality Gates:** Every commit is scanned using SonarQube before building.  
- **Containerization:** Java/Spring Boot packaged as Docker images.  
- **Continuous Delivery with GitOps:** Argo CD keeps production always in sync with Git.  
- **Scalable Deployments:** Helm charts manage Kubernetes deployments.  
- **Zero-Downtime Rollouts:** Safe, automated updates in K8s clusters.  

---

## 🛠️ Tech Stack

| Category            | Tools Used                           |
|--------------------|---------------------------------------|
| CI Server          | Jenkins                               |
| Language/Framework | Java, Spring Boot, Maven              |
| Code Quality       | SonarQube                             |
| Containerization   | Docker                                |
| Orchestration      | Kubernetes (K8s)                      |
| GitOps/CD          | Argo CD                               |
| Package Manager    | Helm                                  |

---

## ⚙️ Architecture & Pipeline Flow

The CI/CD pipeline consists of **8 automated stages** defined in the `Jenkinsfile`:

1. **Checkout** – Clones the source code from GitHub  
2. **Build** – Compiles the Spring Boot application using Maven  
3. **Unit Tests** – Executes JUnit & Mockito tests  
4. **Code Quality Scan** – SonarQube analysis  
5. **Package** – Generates JAR artifacts  
6. **Containerize** – Builds Docker image & pushes to DockerHub  
7. **Deploy (Test Environment)** – Helm deploys to Test namespace  
8. **Deploy (Production)** – Argo CD syncs manifests (GitOps workflow)  

---

## 📂 Repository Structure

├── spring-boot-app/ # Java/Spring Boot application source code
├── spring-boot-app-manifests/ # Kubernetes manifests & Helm charts
├── Jenkinsfile # Complete CI/CD pipeline script
└── ArgoCD/ # Argo CD application + sync configuration


---

# 📦 Short Version (Included as Requested)

## 🔧 Prerequisites
- Java application code hosted on a Git repository  
- Jenkins server  
- Kubernetes cluster  
- Helm package manager  
- Argo CD  

---

## 🪜 Steps

### **1. Install the necessary Jenkins plugins:**
1. Git plugin  
2. Maven Integration plugin  
3. Pipeline plugin  
4. Kubernetes Continuous Deploy plugin  

---

### **2. Create a new Jenkins pipeline**
- Create a pipeline job  
- Configure it with your Git repository URL  
- Add a `Jenkinsfile` to the repository  

---

### **3. Define the pipeline stages**

#### **Stage 1:** Checkout the source code  
#### **Stage 2:** Build using Maven  
#### **Stage 3:** Run unit tests (JUnit, Mockito)  
#### **Stage 4:** Run SonarQube analysis  
#### **Stage 5:** Package JAR  
#### **Stage 6:** Deploy to test environment via Helm  
#### **Stage 7:** Run user acceptance tests (Selenium optional)  
#### **Stage 8:** Promote to production using Argo CD  

---

### **4. Configure Jenkins pipeline stages**
- Git plugin → checkout  
- Maven plugin → build, package  
- SonarQube plugin → analysis  
- Kubernetes Continuous Deploy plugin → Helm deploy  
- Argo CD → promote to production  

---

## 🛠️ 5. Set up Argo CD
- Install Argo CD on Kubernetes  
- Create Git repo for manifests / Helm charts  
- Add Helm chart for the application  
- Configure Argo CD to track the repo  

---

## 🔗 6. Integrate Jenkins with Argo CD
- Add Argo CD API token to Jenkins credentials  
- Update Jenkinsfile to trigger Argo CD deployments  

---

## ▶️ 7. Run the Pipeline
- Trigger Jenkins pipeline  
- Observe each stage  
- Fix issues as needed  

---

# 🧠 What I Learned

- DevOps is not about tools — it’s about **reliability & flow**  
- Breaking production safely teaches real debugging skills  
- Automation works only when the manual process is understood  
- GitOps is the future of cloud-native DevOps  

---

# 🤝 Connect With Me

**Author:** Sohit  
**GitHub:** [sohitji725](https://github.com/sohitji725)

If you're looking for a DevOps/Cloud Engineer who learns by doing and builds real systems—I'd love to connect!

