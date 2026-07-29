# Trend Application Deployment using Terraform, Docker, Jenkins and Amazon EKS

## Project Overview

This project demonstrates the deployment of the Trend React application using a complete CI/CD pipeline. The infrastructure was provisioned using Terraform, the application was containerized using Docker, the Docker image was pushed to Docker Hub, and Jenkins was used to automate the deployment to an Amazon EKS cluster.

## Technologies Used

- React
- Docker
- Docker Hub
- Jenkins
- Terraform
- AWS EC2
- AWS IAM
- AWS VPC
- Amazon EKS
- Kubernetes
- kubectl
- Git
- GitHub

## Repository

Original Repository

https://github.com/Vennilavanguvi/Trend.git

GitHub Repository

https://github.com/harikrishna0015/Trend
## Project Structure

```
Trend/
├── dist/
├── Dockerfile
├── Jenkinsfile
├── deployment.yaml
├── service.yaml
└── README.md
```

## Prerequisites

- AWS Account
- Terraform
- Docker
- AWS CLI
- kubectl
- Jenkins
- Git

## Infrastructure Provisioning

Terraform was used to provision the AWS infrastructure including:

- VPC
- Public Subnet
- Internet Gateway
- Route Table
- Security Group
- IAM Role
- IAM Instance Profile
- EC2 Instance for Jenkins

### Initialize Terraform

```bash
terraform init
```

### Review Execution Plan

```bash
terraform plan
```

### Provision Infrastructure

```bash
terraform apply
```

## Docker

### Build Docker Image

```bash
docker build -t trend-app .
```

### Run Docker Container

```bash
docker run -d -p 3000:80 trend-app
```

## Docker Hub

Docker image was pushed to Docker Hub.

Repository

```
harikrishna2125/trend-app
```

### Login

```bash
docker login
```

### Tag Image

```bash
docker tag trend-app harikrishna2125/trend-app:latest
```

### Push Image

```bash
docker push harikrishna2125/trend-app:latest
```

## Amazon EKS

Amazon EKS was used to host the Kubernetes cluster.

### Verify Cluster

```bash
kubectl get nodes
```

## Kubernetes Deployment

Deploy the application.

```bash
kubectl apply -f deployment.yaml
```

Deploy the service.

```bash
kubectl apply -f service.yaml
```

Verify deployment.

```bash
kubectl get deployments
```

Verify pods.

```bash
kubectl get pods
```

Verify services.

```bash
kubectl get svc
```

The application is exposed using a Kubernetes LoadBalancer service.

## Jenkins CI/CD Pipeline

A Declarative Jenkins Pipeline was created to automate the deployment process.

Pipeline stages include:

1. Source Code Checkout
2. Docker Image Build
3. Docker Image Push to Docker Hub
4. Kubernetes Deployment to Amazon EKS
5. Deployment Verification

## GitHub Integration

The project source code is maintained in GitHub.

GitHub webhook integration can be configured to automatically trigger the Jenkins pipeline whenever code is pushed to the repository.

## Verification

Verify the cluster.

```bash
kubectl get nodes
```

Verify deployments.

```bash
kubectl get deployments
```

Verify pods.

```bash
kubectl get pods
```

Verify services.

```bash
kubectl get svc
```

## Application Access

The application is accessible through the Kubernetes LoadBalancer.

Please see the screenshot inscreenshots folder (Screenshot 2026-07-29 133955)

## Screenshots Included

-Please see in the screenshots folder

## Outcome

Successfully provisioned AWS infrastructure using Terraform.

Successfully containerized the React application using Docker.

Successfully pushed the Docker image to Docker Hub.

Successfully deployed the application to Amazon EKS using Jenkins CI/CD.

Successfully exposed the application using a Kubernetes LoadBalancer service.
