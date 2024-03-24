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

1. Name can be any: devops-ec2-to-codedeploy-role

chose ec2 service

attatch below policies

AmazonEC2RoleforAWSCodeDeploy
AmazonS3FullAccess

2. Name can be any: devops_code_deploy_to_others

chose codedeploy

attatch below policy

AWSCodeDeployRole


less /var/log/aws/codedeploy-agent/codedeploy-agent.log
