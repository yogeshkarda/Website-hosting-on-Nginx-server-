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
⚙️ 3. Install and Configure Nginx
        sudo yum install nginx -y
        sudo systemctl start nginx
        sudo systemctl enable nginx
        sudo systemctl status nginx

Edit Nginx config to act as a reverse proxy:

sudo nano /etc/nginx/nginx.conf
🌐 4. Configure Domain and DNS

Go to your domain registrar (e.g., GoDaddy / Namecheap) and add these A records:

Type	Name	Value (EC2 Public IP)	TTL
A		 @       13.203.197.231        600
A		 www    13.203.197.231        600

🖼️ Screenshot #1: DNS Record Configuration (GoDaddy/Cloudflare panel)

Verify propagation:
nslookup cloudtechkardak.in
🔒 5. Install Certbot & Issue SSL Certificate

Install Certbot:

sudo yum install certbot python3-certbot-nginx -y

Run certificate issuance:

sudo certbot --nginx -d cloudtechkardak.in -d www.cloudtechkardak.in
