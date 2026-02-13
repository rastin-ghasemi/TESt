# AWS ECS Infrastructure with Terraform & CI/CD


<p align="center">
  <img src="Project.png" alt="Project Screenshot" width="800"/>
</p>


This project implements a highly available, scalable containerized application infrastructure on AWS using ECS (Elastic Container Service) with a focus on security, automation, and infrastructure as code, all orchestrated through a comprehensive GitLab CI/CD pipeline.

## Terraform Directory Structure:
The project uses a modular Terraform setup with two main directories:

```txt
Terraform/
├── SetUp/                    # Bootstrap infrastructure (run once)
│   ├── ECR.tf               # Elastic Container Registry repositories
│   ├── IAM.tf               # CI/CD user, roles, and policies
│   ├── main.tf              # Provider and backend config
│   ├── output.tf            # Outputs for Deploy directory
│   └── var.tf               # Variables for Setup
│
└── Deploy/                   # Main infrastructure (CI/CD pipeline)
    ├── ALB.tf               # Application Load Balancer config
    ├── Database.tf           # RDS database instances
    ├── dns.tf               # Route53 DNS records
    ├── ECS.tf               # ECS clusters, tasks, services
    ├── EFS.tf               # Elastic File System for shared storage
    ├── Network.tf           # VPC, subnets, route tables, endpoints
    ├── main.tf              # Provider and backend config
    ├── locals.tf            # Local variables
    ├── output.tf            # Output values
    ├── terraform.tf         # Terraform version/backend settings
    ├── var.tf               # Input variables
    └── templates/           # Task definition templates

```
# Key Components:
- Container Orchestration: ECS clusters running API services and proxy containers across private subnets

- Infrastructure as Code: Terraform with remote state management (S3) and state locking (DynamoDB)

- Storage: EFS for shared persistent storage (NFS) across ECS tasks

- Networking: Private subnet architecture with VPC endpoints for secure AWS service access

- CI/CD Integration: GitLab/GitHub pipelines for automated deployments

## Security:

- ACM for TLS certificate management

- SSH/SSM interface endpoints for secure instance access

- Private network architecture

- Monitoring: CloudWatch integration for logs and metrics

- Container Registry: ECR for Docker image storage

## Architecture Highlights:
- Multi-environment support (dev/staging/prod) through shared resources

- Service-to-service communication via proxy layer

- Secure AWS service access through interface endpoints (ECR, CloudWatch, EFS, SSM)

- Stateless application design with shared EFS for persistent data

This infrastructure provides a production-ready, secure, and scalable platform for running containerized applications with automated deployments and comprehensive monitoring.