# AWS CICD Pipeline Code Deployment to AWS EC2 Instance


<b>User Data for Dependencies installations for AMAZON Linux 2:-</b>

#!/bin/bash<br />
sudo yum -y update<br />
sudo yum -y install ruby<br />
sudo yum -y install wget<br />
cd /home/ec2-user<br />
wget https://aws-codedeploy-ap-south-1.s3.ap-south-1.amazonaws.com/latest/install<br />
sudo chmod +x ./install<br />
sudo ./install auto<br />
sudo yum install -y python-pip<br />
sudo pip install awscli<br />
sudo systemctl restart codedeploy-agent


# Create 2 Roles

1. Name: demo-ec2-to-s3-and-codedeploy

chose ec2 service

attatch below policies

AmazonEC2RoleforAWSCodeDeploy
AmazonS3FullAccess

Attach 1st role to All EC2 instances


2. Name: demo-code-deploy-to-other-services

chose codedeploy

attatch below policy

AWSCodeDeployRole

aws configure
Accesskey:
Secretkey
Region:us-east-1
JSON

CodeDeploy>>>>>>>Applications>>>>create Application>>>>Create deployment group

Goto Pipeline >>>> create pipeline.


less /var/log/aws/codedeploy-agent/codedeploy-agent.log
