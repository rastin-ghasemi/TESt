# AWS ECS Infrastructure with Terraform & CI/CD


<p align="center">
  <img src="Project.png" alt="Project Screenshot" width="800"/>
</p>


This project implements a highly available, scalable containerized application infrastructure on AWS using ECS (Elastic Container Service) with a focus on security, automation, and infrastructure as code.

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