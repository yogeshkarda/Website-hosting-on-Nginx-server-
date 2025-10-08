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
