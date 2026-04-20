# Capstone-Project-Enterprise-AWS-Infrastructure-Deployment

##  Overview
This project demonstrates the design and deployment of a secure, scalable, and highly available AWS infrastructure using a multi-tier architecture.

The architecture simulates a real-world production environment using AWS best practices.

## Architecture Design

The system follows a 3-tier architecture:

- Web Layer: Application Load Balancer (ALB)
- Application Layer: EC2 instances in private subnets
- Data Layer: RDS (MySQL) in private subnets (designed, restricted in sandbox)

## Networking

- Custom VPC (10.0.0.0/16)
- 2 Public Subnets (Multi-AZ)
- 2 Private Subnets (Multi-AZ)
- Internet Gateway configured
- NAT Gateway (designed but restricted in sandbox)
- Route Tables configured

##  Compute Layer

- EC2 instances deployed in private subnets
- Nginx web server installed via UserData
- Instances accessible only via Load Balancer


## Load Balancer

- Application Load Balancer (ALB)
- Distributes traffic across EC2 instances
- Health checks enabled

## Data Layer

- Amazon RDS (MySQL) designed for private access
- Public access disabled
- Access restricted to application layer only
- Deployment limited due to sandbox IAM restrictions

## Security

- Security Groups implemented for all layers
- ALB → EC2 → RDS restricted communication flow
- IAM roles designed (restricted in sandbox)
- Secrets management concept using Parameter Store
- Least Privilege Principle applied

##  Monitoring

- CloudWatch metrics enabled
- CPU utilization alarm configured (>70%)
- ALB metrics monitored via CloudWatch

## Automation (IaC)

- Infrastructure deployed using AWS CloudFormation
- YAML template used for VPC, EC2, and networking components
- Demonstrates Infrastructure as Code principles

##  Limitations

Due to sandbox restrictions:
- NAT Gateway creation was blocked
- RDS subnet group creation was restricted
- IAM role creation was not available

However, full architecture was designed following AWS best practices.


##  Tools Used
- AWS VPC
- EC2
- ALB
- CloudFormation
- CloudWatch


This project demonstrates a production-grade AWS architecture with emphasis on scalability, security, and automation.
