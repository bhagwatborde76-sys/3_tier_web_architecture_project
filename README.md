# 3-Tier Web Architecture on AWS

This project demonstrates a complete **3-Tier Web Architecture** deployed on AWS using VPC, Subnets, Load Balancer, EC2, and RDS.  
Created by **Bhagwat Borde (bhagwatborde76-sys)**.

---

## 🏗 Architecture Overview

This project uses the three-tier model:

### 1️⃣ Presentation Tier (Public Subnet)
- Application Load Balancer (ALB)
- Routes incoming traffic to EC2 instances
- Exposed to the internet

### 2️⃣ Application Tier (Private Subnet)
- EC2 instance running Apache/PHP
- Auto Scaling Group (optional)
- Connected only to Load Balancer

### 3️⃣ Database Tier (Database Subnet)
- Amazon RDS (MySQL)
- Not publicly accessible
- Only EC2 can connect

---

## 🚀 AWS Services Used
- EC2  
- Application Load Balancer (ALB)  
- RDS (MySQL)  
- VPC (Custom)  
- Public & Private Subnets  
- Internet Gateway  
- NAT Gateway  
- Route Tables  
- IAM Roles  
- S3 (optional for logs)  
- CloudWatch (monitoring)  

---

## 📁 Project Structure

