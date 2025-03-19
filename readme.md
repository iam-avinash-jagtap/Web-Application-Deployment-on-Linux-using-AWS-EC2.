# 🚀 Web Application Deployment on Linux using AWS EC2.

## 📌 Project Overview  
This project demonstrates how to deploy a web application on an **AWS EC2 Linux instance** using the **httpd web server**. The setup includes launching an EC2 instance, installing Apache, configuring the firewall, and hosting a sample web application.  
## 🎯 Learning Objectives  
Upon the completion of this project, you will learn:  
- How to launch and manage an **AWS EC2 instance**.  
- How to install and configure the **Apache (httpd) web server**.  
- How to manage **Security groups**.  
- How to deploy a **web application** on Linux.  
- How to ensure a successful deployment. 
## 🛠️ Prerequisites  
Ensure you have the following:  
- An **AWS account** 
- Strong knowledge of **Lniux**
- Basic knowledge of **AWS EC2**  
- A **web application** (HTML) ready for deployment. 

# Steps to Deploy the Web Application  

## Step 1: Launch an AWS EC2 Instance
1. Log in to your **AWS Console**.  
2. Navigate to **EC2 > Instances** and click **Launch Instance**.  
3. Select an **Amazon Linux 2** 
4. Choose an **instance type** (`t2.micro` for free-tier).  
5. Configure the instance settings and add storage if needed.  
6. In the **Security Group** settings, allow:  
   - `HTTP (port 80)` for web access  
   - `SSH (port 22)` for remote access  
7. Launch the instance and connect via SSH.  

## Step 2: Connect to the EC2 Instance
Run the following command to connect to your EC2 instance:  

`ssh -i your-key.pem ec2-user@your-instance-ip`

## Step 3: Update and Install Apache (httpd)
Run the following commands based on your Linux distribution:

        sudo yum update -y
        sudo yum install httpd -y
        sudo systemctl start httpd
        sudo systemctl enable httpd
## Step 4: Deploy the Web Application
1. Navigate to Apache's root directory:

        cd /var/www/html
2. Download web application files:

        wget -o https://www.free-css.com/assets/files/free-css-templates/download/page296/listrace.zip
3. Unzip downloaded file:

        unzip listrace.zip
4. Move all unziped file into root directory:

        mv listrace-html/* /var/www/html
## Step 5: Restart the Apache Web Server

        sudo systemctl restart httpd
## Step 6: Access the Web Application
Open a browser and enter your Server's IP (EC2 public IP):
        http://_your-ec2-public-ip_

![Output](IMG)

# 📌 Conclusion
In this project, we successfully deployed a web application on a Linux machine using AWS resources. We launched an EC2 instance, installed and configured the Apache (httpd) web server, set up firewall rules, and deployed the application files. Finally, we verified that the application was accessible through the instance's public IP. This setup demonstrates an efficient web hosting environment utilizing AWS infrastructure.