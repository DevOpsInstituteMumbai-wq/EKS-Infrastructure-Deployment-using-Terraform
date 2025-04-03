# AWS EKS Infrastructure Deployment

## Overview
This project involves deploying a **highly available, scalable, and secure AWS EKS infrastructure** using **Terraform**. The architecture includes **public and private subnets, an Application Load Balancer (ALB), ECS Containers, a NAT Gateway, an RDS PostgreSQL instance, and an Auto Scaling Group**.

## Problem Statement
The goal is to create an AWS infrastructure that supports containerized applications using **ECS (Elastic Container Service) on EC2 instances**, while ensuring **high availability, security, and scalability**. The deployment should also include an **RDS PostgreSQL database** for data persistence and an **Application Load Balancer (ALB) for handling incoming traffic**.

## Infrastructure Components
The following AWS resources will be provisioned using **Terraform**:

### Networking
- **VPC (Virtual Private Cloud)** with a CIDR block of `10.0.0.0/16`
- **Public and Private Subnets** across multiple Availability Zones (AZs)
- **Internet Gateway** for external access
- **NAT Gateway** for private subnet instances to access the internet

### Compute
- **ECS Cluster** running on EC2 instances within an **Auto Scaling Group**
- **Application Load Balancer (ALB)** for distributing traffic across ECS tasks
- **Security Groups** to control traffic flow between resources

### Database
- **Amazon RDS (PostgreSQL)** instance deployed in the private subnet
- **Subnet Groups and Security Groups** for database access control

### Deployment & Scaling
- **ECS Auto Scaling Group** to manage workload demands dynamically
- **CloudWatch Metrics and Alarms** to monitor resource usage and health

## Prerequisites
Before deploying this infrastructure, ensure you have:
- **Terraform installed** (>= v1.0.0)
- **AWS CLI configured** with appropriate IAM permissions
- **An AWS account** with access to EKS, ECS, and RDS

## Installation & Deployment
### Step 1: Clone the Repository
```sh
git clone https://github.com/your-repo/aws-eks-infra.git
cd aws-eks-infra
```

### Step 2: Initialize Terraform
```sh
terraform init
```

### Step 3: Validate Terraform Configuration
```sh
terraform validate
```

### Step 4: Plan the Deployment
```sh
terraform plan
```

### Step 5: Apply the Configuration
```sh
terraform apply -auto-approve
```

## Outputs
After successful deployment, Terraform will output:
- **EKS Cluster Endpoint**
- **Application Load Balancer DNS Name**
- **RDS Instance Endpoint**
- **Public & Private Subnet IDs**

## Monitoring & Logging
- **CloudWatch Logs** for ECS containers and system monitoring
- **ALB Access Logs** to analyze incoming traffic
- **CloudTrail** for auditing API calls

## Cleanup
To destroy the infrastructure when no longer needed:
```sh
terraform destroy -auto-approve
```

## License
This project is licensed under the MIT License.



