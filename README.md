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

#!/bin/bash
yum update -y
yum install httpd -y
systemctl start httpd
systemctl enable httpd

echo "<h1>Welcome to the 3-Tier Architecture Project</h1>" > /var/www/html/index.html


---

## 🔧 Deployment Steps

### Step 1 — Create VPC
- 1 VPC (10.0.0.0/16)
- 2 Public Subnets
- 2 Private Subnets
- 2 DB Subnets

---

### Step 2 — Create Internet Gateway & NAT Gateway  
- IGW attached to VPC  
- NAT in public subnet for EC2 internet access  

---

### Step 3 — Launch EC2 Instance  
- Use private subnet  
- Apply user-data script  
- Assign IAM Role for S3/RDS  

---

### Step 4 — Create Application Load Balancer  
- Listener: HTTP : 80  
- Target Group: EC2  
- Health Check: `/`  

---

### Step 5 — Setup RDS (MySQL)  
- Engine: MySQL  
- Subnet group: db subnets  
- Disable public access  
- Connectivity only from EC2 SG  

---

## 🔐 Security Best Practices
- EC2 → RDS only (3306)  
- ALB → EC2 only (80)  
- Internet → ALB only  
- No public access to EC2 or RDS  

---

## 🎯 Final Output
- Access your website using ALB DNS  
- Architecture follows industry standards  
- Highly secure 3-tier deployment  

---

## 👨‍💻 Author
**Bhagwat Borde**  
GitHub: https://github.com/bhagwatborde76-sys

