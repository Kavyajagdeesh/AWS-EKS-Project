# Real-Time Game Application on Amazon EKS

## 🎮 Introduction

This project demonstrates the deployment of a *real-time multiplayer game* using *Amazon Elastic Kubernetes Service (EKS). The goal is to build a **resilient, scalable, and low-latency infrastructure* that supports multiple concurrent users while ensuring high availability and seamless gaming performance.

Amazon EKS simplifies Kubernetes management, letting developers focus on application logic while AWS handles the heavy lifting of cluster setup, scaling, and security.

---

## 📚 Table of Contents

1. [Understanding Kubernetes Fundamentals](#understanding-kubernetes-fundamentals)  
   1.1 [EKS vs. Self-Managed Kubernetes: Pros and Cons](#eks-vs-self-managed-kubernetes-pros-and-cons)

2. [Setting Up Your AWS Environment for EKS](#setting-up-your-aws-environment-for-eks)  
   2.1 [Creating an AWS Account and Setting Up IAM Users](#creating-an-aws-account-and-setting-up-iam-users)  
   2.2 [Configuring the AWS CLI and kubectl](#configuring-the-aws-cli-and-kubectl)  
   2.3 [Preparing Networking and Security Groups for EKS](#preparing-networking-and-security-groups-for-eks)

3. [Launching Your First EKS Cluster](#launching-your-first-eks-cluster)  
   3.1 [Using the EKS Console for Cluster Creation](#using-the-eks-console-for-cluster-creation)  
   3.2 [Launching an EKS Cluster via AWS CLI](#launching-an-eks-cluster-via-aws-cli)  
   3.3 [Authenticating with the EKS Cluster](#authenticating-with-the-eks-cluster)

4. [Deploying Applications on EKS](#deploying-applications-on-eks)  
   4.1 [Containerizing Applications with Docker](#containerizing-applications-with-docker)  
   4.2 [Writing Kubernetes Deployment YAMLs](#writing-kubernetes-deployment-yamls)  
   4.3 [Deploying Applications to EKS: Step-by-Step Guide](#deploying-applications-to-eks-step-by-step-guide)

5. [Monitoring and Scaling](#monitoring-and-scaling)  
   5.1 [Integrating CloudWatch and Prometheus](#integrating-cloudwatch-and-prometheus)  
   5.2 [Auto-Scaling and Load Balancing](#auto-scaling-and-load-balancing)

6. [Security and IAM Best Practices](#security-and-iam-best-practices)

7. [Cleanup and Cost Optimization](#cleanup-and-cost-optimization)

---

## 🛠️ Technologies Used

- *Amazon EKS* – Managed Kubernetes service
- *Docker* – Containerization
- *Kubernetes* – Container orchestration
- *AWS CLI & kubectl* – Command-line tools
- *CloudWatch* – Monitoring and logging
- *IAM* – Role-based access control
- *Helm (optional)* – Package manager for Kubernetes

---

## 🚀 Getting Started

### Prerequisites

- AWS account with billing enabled
- IAM user with admin or EKS-related permissions
- Installed tools:
  - awscli
  - kubectl
  - eksctl
  - docker

### Quick Start (Optional)

```bash
# Create EKS Cluster using eksctl
eksctl create cluster --name game-cluster --region us-east-1 --nodegroup-name game-nodes --nodes 2

# Deploy your Dockerized game app
kubectl apply -f game-deployment.yaml

