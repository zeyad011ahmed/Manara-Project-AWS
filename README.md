# AWS 3-Tier Architecture for Web Application

## ⚙️ Project Overview

This architecture hosts a scalable web application on AWS using a 3-tier model (Web, Application, Database). It leverages AWS Auto Scaling, RDS, and CloudWatch for resilience and monitoring.

## 📊 Architecture Diagram

![Architecture](./AWS-Manara/Project.jpg)

## 🧹 Components Breakdown

### 1. Web Tier

* EC2 Instances (Auto Scaling)
* Public Subnet
* Load Balanced across Availability Zones

### 2. Application Tier

* EC2 Instances (Auto Scaling)
* Public Subnet
* Stateless applications, scalable

### 3. Data Tier

* Amazon RDS (Multi-AZ)
* Private Subnets
* One Primary DB, One Standby

### 4. Monitoring and Notifications

* AWS CloudWatch for metrics & logs
* SNS Topic for alerts
* Email Notifications via Gmail

## ⚙️ Deployment Steps

1. **Create VPC & Subnets**

   * 4 Public & 2 Private subnets across 2 AZs

2. **Deploy EC2 Web & App Instances**

   * Configure Auto Scaling Groups
   * Security Groups for access control

3. **Deploy RDS Instance**

   * Enable Multi-AZ
   * Set up private subnet group

4. **Set up Monitoring**

   * Create CloudWatch Alarms
   * Configure SNS and subscribe email

## 🛡 Security

* Public subnets restricted to web/app ports
* Private subnets for database only
* IAM roles for EC2 access

## 📩 Alerts

* Example: CPU > 70% triggers CloudWatch Alarm
* Alarm notifies SNS, which sends email

## 💡 Major Benefits

* **High Availability**: ALB and ASG ensure minimal downtime.
* **Scalability**: Auto Scaling dynamically adjusts resources as needed.
* **Security**: IAM, Security Groups, and private networking enhance system protection.
* **Cost Optimization**: Resources scale up and down based on demand, reducing unnecessary expenses.

## 🧠 Notes

* All infrastructure is in high availability mode.
* This AWS-based 3-tier architecture provides a reliable, secure, and cost-efficient way to deploy scalable web applications. By leveraging AWS managed services, the system achieves operational efficiency and ensures business continuity.
* Can be deployed with Terraform/CloudFormation for IaC.
