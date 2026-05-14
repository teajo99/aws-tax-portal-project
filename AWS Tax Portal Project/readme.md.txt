# 🚀 AWS Government Tax Filing Portal (Highly Available Architecture)

## 📌 Overview

This project demonstrates a highly available and scalable web application simulating a **Government Tax Filing System** built on Amazon Web Services.

It showcases how modern cloud applications handle:
- High traffic
- Automatic scaling
- Fault tolerance
- Load balancing
- Infrastructure resilience

Built using core AWS services like EC2, VPC, ELB, ASG, and SNS.

---

## 🏗️ Architecture


---

## ☁️ AWS Services Used

- EC2 (Virtual Servers)
- VPC (Network Isolation)
- Internet Gateway (Public Access)
- Application Load Balancer (Traffic Distribution)
- Auto Scaling Group (Scaling + Self-Healing)
- Target Tracking Policy (CPU-based scaling)
- SNS (Notifications)

---

## ⚙️ Features

- Highly available architecture across 2 Availability Zones
- Auto scaling based on CPU utilization
- Load balancing across multiple EC2 instances
- Automatic replacement of unhealthy instances
- Real-time infrastructure notifications via SNS
- Web application deployed using Apache HTTP Server

---

## 🧪 Deployment Steps

### 1. VPC Setup
- Created custom VPC
- Configured 2 public subnets in different Availability Zones
- Attached Internet Gateway
- Configured route tables for internet access

---

### 2. EC2 Configuration
- Launch Template created
- Apache installed via User Data script
- Auto-assign public IP enabled

---

### 3. Load Balancer
- Application Load Balancer created
- Listener configured on port 80
- Connected to Target Group

---

### 4. Auto Scaling Group
- Desired capacity: 2
- Min capacity: 2
- Max capacity: 4
- Linked to Target Group

---

### 5. Scaling Policy
- Target tracking policy based on CPU utilization
- Target: 50%

---

### 6. SNS Notifications
- Email notifications configured
- Alerts for:
  - Instance launch
  - Instance termination
  - Scaling events

---

## 🧾 User Data Script

The EC2 instances are automatically configured using the following script:

- Installs Apache (httpd)
- Starts web server
- Deploys web page

---

## 🌐 Web Application

The application displays:

- Government Tax Filing System
- Instance hostname (dynamic)
- AWS VPC deployment confirmation

Example:



---

## 🧠 Key Learning Outcomes

- Designing scalable cloud architectures
- Understanding load balancing concepts
- Implementing auto scaling strategies
- Working with VPC networking
- Debugging real AWS deployment issues
- Understanding health checks and failure recovery

---

## 🛠️ Issues Faced & Resolved

### 1. 502 Bad Gateway
- Cause: Unhealthy EC2 instances
- Fix: Corrected security groups and Apache configuration

### 2. SSH Timeout
- Cause: Using private IP instead of public IP
- Fix: Enabled public IP in Launch Template

### 3. Health Check Failures
- Cause: Missing or misconfigured web server
- Fix: Installed and configured Apache correctly

### 4. Bash Variable Not Rendering
- Cause: Incorrect heredoc quoting
- Fix: Removed single quotes from EOF block

---

## 📊 Final Result

A fully working cloud architecture that:
- Handles traffic distribution via ALB
- Scales automatically using ASG
- Self-heals failed instances
- Sends operational alerts via SNS
- Runs securely inside a custom VPC

---

## 👨‍💻 Author

Cloud Engineering Project demonstrating real-world AWS architecture design and troubleshooting skills.

