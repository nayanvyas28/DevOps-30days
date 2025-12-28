# Day 04 – AWS Basics for DevOps

## What is EC2?
EC2 (Elastic Compute Cloud) provides virtual servers on the cloud.

EC2 is used to:
- Host applications
- Run Docker containers
- Deploy CI/CD tools
- Run Kubernetes nodes

---

## EC2 Key Concepts
- Instance → Virtual server
- AMI → OS image (Ubuntu, Amazon Linux)
- Instance Type → CPU & RAM (t2.micro)
- Key Pair → SSH authentication
- Security Group → Virtual firewall

---

## IAM (Identity and Access Management)
IAM controls access to AWS services.

IAM Components:
- Users → human access
- Roles → service access
- Policies → permissions

Best practice:
- Never use root account for daily work

---

## Security Groups
Security Groups act as firewalls for EC2.

Inbound rules example:
- SSH → Port 22
- HTTP → Port 80

Outbound rules:
- Allow all traffic (default)

---

## SSH into EC2
SSH is used to access cloud servers.

Command:
ssh -i key.pem ubuntu@public_ip

---

## Manual Deployment Example
Install Nginx on EC2:
sudo apt update
sudo apt install nginx -y

Check in browser:
http://public_ip

---

## What I Learned Today
- Basics of cloud computing
- AWS EC2 architecture
- IAM and security basics
- Launching EC2 instance
- SSH access to cloud server
- Manual app deployment

---

## Interview Notes
- EC2 provides virtual servers
- Security Groups control traffic
- IAM manages permissions
- SSH is used to access EC2
