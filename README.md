# Cloud Architecture Project

## Overview
This project implements a scalable, multi-cloud architecture centered on AWS infrastructure with integrations to Google Cloud and Microsoft Azure for specialized analytics and AI services. The architecture uses Kubernetes for containerized applications with a microservices approach.

## Architecture Components

### Infrastructure as Code
- **Terraform**: Manages infrastructure provisioning across cloud providers
- **GitHub**: Hosts source code and triggers CI/CD workflows

### AWS Resources
- **AWS Region**: Primary hosting environment
- **Amazon VPC**: Secure network isolation
- **Private Subnet**: Enhanced security for critical components
- **Amazon EKS Cluster**: Managed Kubernetes service hosting our application
  - Frontend and backend services deployed as pods
  - Organized into distinct service groups
- **Load Balancer**: Distributes traffic to the Kubernetes cluster
- **Amazon DynamoDB**: NoSQL database for structured data
- **Amazon S3**: Object storage for files and assets
- **Amazon Bedrock**: AI foundation model services
- **AWS Lambda**: Serverless functions for event processing
- **AWS CodePipeline/CodeBuild**: CI/CD pipeline automation
- **Amazon ECR**: Container registry for Docker images

### Multi-Cloud Integrations
- **Google Cloud**:
  - BigQuery for real-time analytics
- **Microsoft Azure**:
  - Azure AI Language Services for sentiment analysis

### Application Components
- **cloudmart-frontend**: User interface services
- **cloudmart-backend**: Business logic and API services
- **Event-driven microservice**: Architecture for real-time processing

## Deployment Flow
1. Code is pushed to GitHub
2. AWS CodePipeline triggers a build process
3. AWS CodeBuild builds the container images
4. Images are stored in Amazon ECR
5. EKS cluster deploys the updated containers
6. Infrastructure changes are managed via Terraform

## Getting Started

### Prerequisites
- AWS CLI configured with appropriate permissions
- kubectl installed and configured
- Terraform installed
- Docker installed
- Access to required AWS services

### Installation
```bash
# Clone the repository
git clone https://github.com/your-org/cloud-architecture-project.git
cd cloud-architecture-project

# Initialize Terraform
terraform init

# Apply the infrastructure
terraform apply

```

### Deployment
```bash
# Deploy application to EKS
kubectl apply -f kubernetes/
```

## Video Demo

[Project Demo Video]
[Download the demo video](./Demo_video.mp4)

## Security Considerations
- All data in transit is encrypted
- Private subnets used for sensitive components
- IAM roles configured with least privilege principle
- Regular security audits performed

## Contributing
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

