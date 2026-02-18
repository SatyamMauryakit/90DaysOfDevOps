# Day 08 – Cloud Server Setup: Docker, Nginx & Web Deployment

This project demonstrates deploying a Linux cloud server, installing Docker and Nginx, configuring firewall rules, and verifying a live web server accessible from the internet.

Part of the **90 Days of DevOps** learning journey.

tep 1: Create Cloud Instance (AWS EC2)

Login to AWS Console

Go to EC2 → Launch Instance

Name: day08-server

AMI: Ubuntu 22.04 LTS

Instance Type: t2.micro (Free Tier)

Key Pair: create/download


chmod 400 day08.pem

ssh -i day08.pem ubuntu@<your-public-ip>

✅ Part 2: Install Docker & Nginx
Step 1: Update System
sudo apt update
sudo apt upgrade -y

Step 2: Install Docker
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
docker --version

Step 3: Install Nginx
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx

Verify Nginx
systemctl status nginx




