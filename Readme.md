# AWS Highly Available Web Application

## Project Overview
This project demonstrates a Highly Available Web Application architecture deployed on AWS using multiple Availability Zones and an Application Load Balancer.

The infrastructure is designed to improve fault tolerance, scalability, and reliability by distributing traffic across multiple EC2 instances.

# AWS Services Used
- Amazon EC2
- Amazon VPC
- Application Load Balancer
- Target Groups
- Security Groups
- Public Subnets
- Internet Gateway

# Architecture Diagram


# Project Objectives
- Deploy EC2 instances across multiple Availability Zones
- Configure an Application Load Balancer
- Achieve High Availability and Fault Tolerance
- Distribute traffic between multiple servers
- Simulate real-world cloud architecture

# Infrastructure Setup

## Availability Zones
- AZ1
- AZ2

## EC2 Instances
- WebServer-AZ1
- WebServer-AZ2

## Load Balancer
- Internet-facing Application Load Balancer

# Deployment Steps
1. Created custom VPC
2. Configured public subnets in different AZs
3. Configured route tables and Internet Gateway
4. Created Security Groups
5. Launched EC2 instances
6. Installed Apache Web Server
7. Created custom webpages for each server
8. Configured Target Group
9. Attached EC2 instances to Load Balancer
10. Tested High Availability and Failover

# High Availability Test
One EC2 instance was stopped intentionally to simulate server failure.

Result:
- Website remained accessible
- Load Balancer redirected traffic automatically to healthy server

# Security Configuration
- SSH access restricted
- HTTP access enabled
- Security Group based traffic filtering
- Separate Availability Zone deployment

# Key Learnings
- Multi AZ deployment
- Application Load Balancer configuration
- Target Group health checks
- Fault tolerance implementation
- AWS networking concepts

# Screenshots

(Add screenshots here)

---

# Future Improvements
- Auto Scaling Group
- HTTPS with ACM
- Route 53 custom domain
- Terraform automation
- CloudWatch monitoring

# Author

Muhammad Hammad