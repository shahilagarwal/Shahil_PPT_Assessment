**ASG and ELB in EC2** 

**Simple Definition** 

- Configure Auto Scaling Group with Load Balancer to automatically scale EC2 instances and distribute traffic. 

**Objective** 

- Understand Auto Scaling concept 
- Understand Load Balancing concept 
- Learn High Availability architecture 
- Maintain uptime during traffic spikes 
- Implement scaling in Amazon Web Services 

**Concept Overview** 

**Auto Scaling Group** 

- Automatically launches EC2 instances 
- Automatically terminates instances 
- Maintains desired capacity 

**Elastic Load Balancer** 

- Distributes incoming traffic across multiple EC2 instances 
- Routes traffic only to healthy instances 

**High Availability** 

- If one instance fails, traffic is redirected to healthy instances 
- Multi Availability Zone deployment ensures fault tolerance 

**Step by Step Implementation** 

**Step 1 Create Launch Template** 

- Go to EC2 Dashboard 
- Click Launch Templates 
- Click Create Launch Template 
- Enter template name 
- Select Ubuntu 22.04 AMI 
- Select instance type t2.micro 
- Select key pair 
- Configure security group to allow HTTP 80 and SSH 22 
- Add user data script if required 

User data example 

#!/bin/bash 

apt update -y 

apt install nginx -y 

systemctl start nginx 

systemctl enable nginx 

echo "Welcome from ASG Instance" > /var/www/html/index.html 

- Click Create Launch Template 

**Step 2 Create Target Group** 

- Go to Target Groups 
- Click Create Target Group 
- Select Target type Instances 
- Protocol HTTP 
- Port 80 
- Select VPC 
- Click Create 

**Step 3 Create Load Balancer** 

- Go to Load Balancers 
- Click Create Load Balancer 
- Select Application Load Balancer 
- Choose Internet facing 
- Listener HTTP port 80 
- Select at least two Availability Zones 
- Attach previously created Target Group 
- Click Create 

**Step 4 Create Auto Scaling Group** 

- Go to Auto Scaling Groups 
- Click Create Auto Scaling Group 
- Select Launch Template 
- Select VPC and at least two subnets 
- Attach existing Load Balancer 
- Select Target Group 
- Set Desired capacity 2 
- Set Minimum capacity 1 
- Set Maximum capacity 3 
- Click Create 

**Step 5 Configure Scaling Policy** 

- Open Auto Scaling Group 
- Go to Automatic Scaling 
- Click Add Policy 
- Select Target Tracking Policy 
- Choose Average CPU Utilization 
- Set Target value 60 percent 
- Click Create 

**Step 6 Test the Setup** 

- Copy Load Balancer DNS name 
- Open in browser using http 
- Verify website loads 
- Increase CPU load to test scaling 
- Observe new instance launch when CPU increases 
- Observe instance termination when load decreases 

**Final Outcome** 

- Launch Template created 
- Target Group created 
- Load Balancer configured 
- Auto Scaling Group attached to Load Balancer 
- Scaling policy enabled 
- High Availability achieved 
