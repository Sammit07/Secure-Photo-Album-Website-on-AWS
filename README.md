# 📷 Secure Photo Album Website on AWS

The **Photo Album Website** is a secure cloud-hosted web application deployed on **Amazon Web Services (AWS)**.  
It allows users to view photo albums, with metadata stored in a **MySQL RDS database** and photos served from **Amazon S3**.   

<img width="871" height="606" alt="image" src="https://github.com/user-attachments/assets/785acf6c-23c0-4675-9da9-68f46eee38fa" />

---

## 📌 Features

- 🌐 **Cloud-Hosted Website**: PHP-based photo album accessible via Elastic IP.  
- 🛡️ **Secure Networking**: VPC with public/private subnets, security groups, and network ACLs.  
- 🗄️ **Database Integration**: MySQL RDS for storing photo metadata with phpMyAdmin for management.  
- 📂 **Scalable Storage**: Amazon S3 bucket for serving photo content.  
- ⚙️ **Reliable Infrastructure**: High availability setup with multiple subnets and Elastic IP allocation.  
- 🔒 **Cloud Security**: Least-privilege access policies, isolated database subnet, and restricted traffic flows.  

---

## 🌟 Project Overview

The project was built step by step, following a structured approach:  

### 🔹 Step 1: VPC and Subnet Design
- Created a dedicated **VPC (SRautVPC)** with a CIDR block.  
- Designed **four subnets** (two public, two private) across availability zones for redundancy.  

### 🔹 Step 2: Internet Gateway & Routing
- Configured an **Internet Gateway (myIGW)** for public internet access.  
- Linked public subnets to the gateway using **route tables**.  

### 🔹 Step 3: Security Configuration
- Created **Security Groups** for web server, database server, and test instances.  
- Applied **Network ACLs** for subnet-level control, following least-privilege principles.  

### 🔹 Step 4: EC2 Instance Deployment
- Launched an **EC2 instance** with Amazon Linux 2 to act as the web server.  
- Installed **Apache, PHP, and phpMyAdmin** for web and DB management.  
- Deployed a **test instance** in a private subnet for validation.  

### 🔹 Step 5: Elastic IP Allocation
- Allocated and attached an **Elastic IP** for a static and reliable public-facing web server.  

### 🔹 Step 6: RDS Database Setup
- Deployed a **MySQL 8.0.34 RDS instance** in a private subnet.  
- Linked the database to phpMyAdmin for secure management.  
- Created a **Photos table** for storing image metadata.  

### 🔹 Step 7: S3 Bucket Integration
- Provisioned an **Amazon S3 bucket** for photo storage.  
- Configured a **bucket policy** for public read-only access.  
- Verified successful uploads and retrieval of photos.  

### 🔹 Step 8: PHP Website Deployment
- Updated `constants.php` with database and S3 details.  
- Ensured correct directory structure and permissions.  
- Launched the **Photo Album Website**.  

### 🔹 Step 9: Testing & Verification
- **Functional Testing**: Verified photo listing and metadata display.  
- **Security Testing**: Checked SSH access restrictions, ICMP responses, and DB access.  

---

## 🏗️ Architecture

<img width="849" height="615" alt="image" src="https://github.com/user-attachments/assets/e1c6037b-bedc-4ded-9a79-a692ec13dc3d" />


---

## 🛠️ Tech Stack

- **Cloud Infrastructure**: AWS VPC, Subnets, Internet Gateway, Elastic IP  
- **Compute**: Amazon EC2 (Apache + PHP)  
- **Database**: Amazon RDS (MySQL 8.0.34) + phpMyAdmin  
- **Storage**: Amazon S3 for image hosting  
- **Networking & Security**: Security Groups, Network ACLs, IAM policies  
- **Languages & Tools**: PHP, SQL, Apache, phpMyAdmin  

---

## 🔒 Security Best Practices

- Database hosted in a **private subnet** with no direct internet access.  
- **Security Groups** restrict MySQL access only to the web server.  
- **Network ACLs** enforce least-privilege traffic rules.  
- **IAM roles and policies** configured to limit S3 and RDS access.  

---

## 🚀 Future Enhancements

- 🔐 Add user authentication for photo uploads.  
- ⚡ Use **CloudFront CDN** for faster image delivery.  
- 🔒 Enable **HTTPS with AWS Certificate Manager (ACM)**.  
- 📈 Implement **auto-scaling with an Elastic Load Balancer** for high traffic.  
