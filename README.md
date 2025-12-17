# Dockerized Web Application on AWS EC2 with Application Load Balancer
This project demonstrates deploying a Dockerized Nginx web application on multiple AWS EC2 instances and exposing it to the internet using an Application Load Balancer (ALB).
The load balancer distributes traffic across EC2 instances and performs health checks to ensure high availability.

# Used services
EC2 instances 2
security group 2
Load balancer
Git /github
Target Group

# security group configruation
Load balancer security group

Type   Port   Source
HTTP    80     0.0.0.0/0

EC2 security group
Type   Port   Source
HTTP   80     load balancer security group
ssh    22     0.0.0.0/0

# Implemented steps
Launch 2 EC2 instances

# Connect that 
Install Docker    
sudo yum update -y
sudo yum install docker -y
sudo systemctl start docker
sudo systemctl enable docker

# Build docker image 
docker build -t imagename .
# Run Docker Container
docker run -d -p 80:80 image name

# Create Target Group
register both instances 

# Create application load balancer
attach load balancer SG

# Verify
Target Group status shows Healthy

Access the application using:
http://<ALB-DNS-Name>

