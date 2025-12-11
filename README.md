# Jenkins Pipeline for Java based application using Maven, SonarQube, Argo CD, Helm and Kubernetes

![Screenshot 2023-03-28 at 9 38 09 PM](https://user-images.githubusercontent.com/43399466/228301952-abc02ca2-9942-4a67-8293-f76647b6f9d8.png)


# 📘 **README.md (Generated)**

```markdown
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

```

.
├── spring-boot-app/              # Java/Spring Boot application source code
├── spring-boot-app-manifests/    # Kubernetes manifests & Helm charts
├── Jenkinsfile                    # Complete CI/CD pipeline script
└── ArgoCD/                        # Argo CD application + sync configuration

````

---

## 🚀 Getting Started

Follow the steps below to replicate this CI/CD pipeline.

---

### ### **Prerequisites**
Before starting, ensure the following are installed:

- Kubernetes Cluster (Minikube, EKS, GKE, etc.)
- Jenkins server with Docker access
- Helm
- SonarQube server
- Argo CD installed on the K8s cluster

---

## 🛠️ Installation Steps

### **1. Jenkins Setup**
Install plugins:
- Git
- Maven Integration
- Pipeline
- Kubernetes Continuous Deploy
- SonarQube Scanner

Configure:
- JDK
- Maven
- SonarQube server credentials
- DockerHub credentials

---

### **2. Install Argo CD**

```bash
kubectl create namespace argocd
kubectl apply -n argocd \
  -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
````

Access Argo CD UI by port-forwarding:

```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

---

### **3. Create CI/CD Pipeline in Jenkins**

* Create a *Pipeline Job*
* Point it to your repository URL
* Make sure the `Jenkinsfile` path is correct
  (default: `./Jenkinsfile`)

---

### **4. Configure GitHub Webhooks**

In your GitHub repo:

* Go to **Settings → Webhooks**
* Add Jenkins webhook URL
  `http://<jenkins-url>/github-webhook/`
* Trigger events: **Push** & **PR merges**

---

## 🧠 What I Learned

Building this project taught me:

* **DevOps ≠ Tools** — It’s about reliability, resilience, and flow
* **Breaking production safely** teaches real debugging skills
* Automation is effective only when the manual process is well understood
* **GitOps** is the future of cloud-native and declarative infrastructure

---

## 🤝 Connect With Me

**Author:** Sohit
**GitHub:** [sohitji725](https://github.com/sohitji725)

If you're looking for a DevOps/Cloud Engineer who learns by doing and builds real systems—I'd love to connect!

---

```



✅ A shorter version  
Prerequisites:

   -  Java application code hosted on a Git repository
   -   Jenkins server
   -  Kubernetes cluster
   -  Helm package manager
   -  Argo CD

Steps:

    1. Install the necessary Jenkins plugins:
       1.1 Git plugin
       1.2 Maven Integration plugin
       1.3 Pipeline plugin
       1.4 Kubernetes Continuous Deploy plugin

    2. Create a new Jenkins pipeline:
       2.1 In Jenkins, create a new pipeline job and configure it with the Git repository URL for the Java application.
       2.2 Add a Jenkinsfile to the Git repository to define the pipeline stages.

    3. Define the pipeline stages:
        Stage 1: Checkout the source code from Git.
        Stage 2: Build the Java application using Maven.
        Stage 3: Run unit tests using JUnit and Mockito.
        Stage 4: Run SonarQube analysis to check the code quality.
        Stage 5: Package the application into a JAR file.
        Stage 6: Deploy the application to a test environment using Helm.
        Stage 7: Run user acceptance tests on the deployed application.
        Stage 8: Promote the application to a production environment using Argo CD.

    4. Configure Jenkins pipeline stages:
        Stage 1: Use the Git plugin to check out the source code from the Git repository.
        Stage 2: Use the Maven Integration plugin to build the Java application.
        Stage 3: Use the JUnit and Mockito plugins to run unit tests.
        Stage 4: Use the SonarQube plugin to analyze the code quality of the Java application.
        Stage 5: Use the Maven Integration plugin to package the application into a JAR file.
        Stage 6: Use the Kubernetes Continuous Deploy plugin to deploy the application to a test environment using Helm.
        Stage 7: Use a testing framework like Selenium to run user acceptance tests on the deployed application.
        Stage 8: Use Argo CD to promote the application to a production environment.

    5. Set up Argo CD:
        Install Argo CD on the Kubernetes cluster.
        Set up a Git repository for Argo CD to track the changes in the Helm charts and Kubernetes manifests.
        Create a Helm chart for the Java application that includes the Kubernetes manifests and Helm values.
        Add the Helm chart to the Git repository that Argo CD is tracking.

    6. Configure Jenkins pipeline to integrate with Argo CD:
       6.1 Add the Argo CD API token to Jenkins credentials.
       6.2 Update the Jenkins pipeline to include the Argo CD deployment stage.

    7. Run the Jenkins pipeline:
       7.1 Trigger the Jenkins pipeline to start the CI/CD process for the Java application.
       7.2 Monitor the pipeline stages and fix any issues that arise.

This end-to-end Jenkins pipeline will automate the entire CI/CD process for a Java application, from code checkout to production deployment, using popular tools like SonarQube, Argo CD, Helm, and Kubernetes.
