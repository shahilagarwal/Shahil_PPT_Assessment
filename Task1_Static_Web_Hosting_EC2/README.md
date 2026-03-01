**Static Web Hosting on EC2 using Ubuntu and Nginx**  
**Overview**

This task demonstrates how to deploy a static website on an Amazon EC2 instance running Ubuntu Server and configure Nginx as the web server.

The goal of this project is to provide hands-on experience with:

\-   Amazon EC2 instance provisioning  
\-   Secure Shell (SSH) access  
\-   Linux server administration  
\-   Nginx installation and configuration  
\-   Static website deployment  
\-   Basic cloud security configuration

 **Project Architecture**  
\-   Step 1: Launch EC2 Instance  
\-   Step 2: Configure Security Group  
\-   Step 3: Connect via SSH  
\-   Step 4: Update the Server  
\-   Step 5: Install and Configure Nginx  
\-   Step 6: Deploy Static Website  
\-   Step 7: Verify Deployment

Client Browser → Public IP → EC2 (Ubuntu) → Nginx → Static HTML Files

**Step By Step Process : \-** 

Step 1: Launch EC2 Instance

1\.  Log in to AWS Management Console.  
2\.  Navigate to the EC2 Dashboard.  
3\.  Click \*\*Launch Instance\*\*.

Instance Configuration

\-   Name: MyStaticWebsite  
\-   AMI: Ubuntu Server 22.04 LTS (Free Tier eligible)  
\-   Instance Type: t2.micro  
\-   Key Pair: Create a new key pair and download the \`.pem\` file

Keep the \`.pem\` file secure. It is required for SSH access.

Launch the instance and wait until its state becomes \*\*Running\*\*.

Step 2: Configure Security Group

Configure inbound rules as follows:

  Type   Port   Source  
  \------ \------ \----------------------  
  SSH    22     My IP  
  HTTP   80     Anywhere (0.0.0.0/0  
This ensures secure server access and public web access.

Step 3: Connect via SSH

chmod 400 your-key.pem\\  
ssh \-i your-key.pem ubuntu@your-public-ip

Step 4: Update the Server

After successful login:

sudo apt update  
sudo apt upgrade \-y

This ensures the server packages are up to date.

Step 5: Install and Configure Nginx

Install Nginx:

sudo apt install nginx \-y

Verify installation:

sudo systemctl status nginx

If active, Nginx is successfully installed.

Step 6: Deploy Static Website

Nginx default root directory:

/var/www/html

Navigate to the directory:

cd /var/www/html

Paste the index.html file of your static web app inside the /var/www/html

Step 7: Verify Deployment

Open a browser and navigate to:

http://your-public-ip

If configured correctly, your custom webpage should appear.

