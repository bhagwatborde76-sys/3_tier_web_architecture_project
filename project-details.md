# Project Details – 3-Tier AWS Architecture

This document explains the design, configuration, and deployment of the 3-tier architecture on AWS.

## Overview
The goal is to deploy a secure, scalable, and highly available web application on AWS.

## 3 Layers

### 1. Presentation Layer
- Application Load Balancer (ALB)
- Public Subnet
- Exposed to users

### 2. Application Layer
- EC2 Instances in Private Subnet
- Apache Web Server
- Auto Scaling enabled (optional)

### 3. Database Layer
- RDS MySQL
- Multi-AZ (optional)
- Not publicly accessible

## Networking
- Custom VPC
- Public + Private + DB Subnets
- Route Tables
- IGW + NAT Gateway

## Security Groups
- LB: HTTP from internet
- EC2: HTTP only from LB
- RDS: 3306 only from EC2

## Final Output
- Access website using ALB DNS
- Secure backend with RDS
