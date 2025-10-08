Website hosting on Nginx server
This project demonstrates how to host a **static website** (HTML/CSS/JS) on a **Linux EC2 instance**, configure it with **both Nginx and Apache**, attach a **custom domain**, and secure it using **Let's Encrypt (Certbot)** with automatic **HTTP → HTTPS redirection**.
## ⚙️ Architecture Overview

**Components Used:**
- **AWS EC2 (Linux Instance)** – Hosting server  
- **Nginx** – Reverse proxy and HTTPS handler  
- **Apache (HTTPD)** – Serves static content  
- **Custom Domain** – here I used free domain website hostia.com 
- **Certbot (Let’s Encrypt)** – Issues and manages free SSL certificates  

**Flow:**
`Client → Nginx (HTTPS) → Apache (Static Website Files)`
## 🚀 Step-by-Step Deployment Guide

### 🖥️ 1. Launch EC2 Instance
1. Log in to your AWS Console.  
2. Launch an **Amazon Linux 2** or **Ubuntu 22.04** instance.  
3. Configure:
   - **Security Group**: Allow ports `22`, `80`, `443`.  
   - **Key Pair**: Create or use an existing key pair.  
4. Connect to instance via SSH:
   ```bash
   I access this linux server using putty
Install and Configure Nginx
sudo yum install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
sudo systemctl status nginx
