# 🚀 CI/CD Pipeline for NestJS App using Jenkins, Docker & AWS EC2

This project demonstrates a **fully automated CI/CD pipeline** for a **NestJS application** using **Jenkins**, **Docker**, **AWS EC2**, and **GitHub**.  
After every successful deployment, an **email notification** is sent to confirm the deployment status.

---

## 🧩 Tech Stack

- **Backend Framework**: NestJS (Node.js)
- **Version Control**: Git & GitHub
- **CI/CD Tool**: Jenkins
- **Containerization**: Docker
- **Cloud Platform**: AWS EC2 (Ubuntu)
- **Notification**: Email (SMTP)
- **OS**: Ubuntu 22.04 LTS

---

## 🏗️ Architecture Overview

```text
Developer (Git Push)
        |
        v
GitHub Repository
        |
        v
Jenkins Pipeline
        |
        +--> Build Docker Image
        |
        +--> Run Container
        |
        +--> Deploy to AWS EC2
        |
        +--> Email Notification
        |
        v
NestJS Application Live 🚀
