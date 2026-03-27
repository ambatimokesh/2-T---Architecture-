Azure 2-Tier Architecture with Public & Private Load Balancer
📌 Project Overview

This project demonstrates the implementation of a 2-tier architecture in Microsoft Azure using:

Web Tier → NGINX Web Server
Application Tier → Apache Tomcat
Load Balancing → Public & Private Load Balancers

The architecture ensures scalability, security, and efficient traffic distribution between tiers.

🏗️ Architecture Diagram



⚙️ Technologies Used
Microsoft Azure
Virtual Machines (VMs)
Virtual Network (VNet)
Network Security Groups (NSG)
NGINX
Apache Tomcat
Public Load Balancer
Private Load Balancer
📂 Project Steps
🔹 Step 1: Resource Creation
Created a Resource Group
Created Virtual Machines for:
Web Server
Application Server
🔹 Step 2: Networking Configuration
Created a Virtual Network (VNet)
Configured Subnets:
Web Subnet → Web Server
App Subnet → Application Server
🔹 Step 3: Web Server Setup (NGINX)

Installed NGINX on Web Server:

#!/bin/bash
sudo su
apt update
apt install nginx -y
🔹 Step 4: Application Server Setup
Created VM for Application Server
Placed it inside App Subnet
🔹 Step 5: NSG Configuration

Configured security rules:

Web Server NSG

Allow Port 80 (HTTP)

App Server NSG

Allow Port 8080 (Tomcat)
🔹 Step 6: Initial Testing
Accessed Web Server using Public IP
Verified NGINX default page
🔹 Step 7: Public Load Balancer (Web Tier)

Configured:

Frontend IP → Public
Backend Pool → Web VM
Health Probe → Port 80
Rule → HTTP (Port 80)

📌 Handles incoming internet traffic

🔹 Step 8: Private Load Balancer (App Tier)

Configured:

Frontend IP → Private (App Subnet)
Backend Pool → App VM
Health Probe → Port 8080
Rule → Port 8080

📌 Ensures secure internal communication

🔹 Step 9: Tomcat Installation (App Server)
sudo su
apt update
apt install default-jdk -y
apt install tomcat10
🔹 Step 10: Connectivity Testing
telnet <App-Private-IP> 8080

✅ Verified successful communication between:

Web Tier → App Tier
🔐 Security Implementation
Used NSG rules to restrict traffic
Separated tiers using subnets
Internal communication via Private Load Balancer
📊 Key Features
✔️ Scalable architecture
✔️ Secure communication between tiers
✔️ Load-balanced traffic handling
✔️ Real-world cloud deployment scenario
✅ Conclusion

This project successfully demonstrates:

2-tier architecture deployment in Azure
Public Load Balancer for external access
Private Load Balancer for internal traffic
Secure and efficient cloud design
👨‍💻 Author

Ambati Mokesh Reddy
🎓 BCA Graduate | ☁️ Aspiring Cloud
