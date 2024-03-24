# AWS CICD Pipeline Code Deployment to AWS EC2 Instance


<b>User Data for Dependencies installations for AMAZON Linux 2:-</b>
```bash
#!/bin/bash
sudo yum -y update
sudo yum -y install ruby
sudo yum -y install wget
cd /home/ec2-user
wget https://aws-codedeploy-ap-south-1.s3.ap-south-1.amazonaws.com/latest/install
sudo chmod +x ./install
sudo ./install auto
sudo yum install -y python-pip
sudo pip install awscli
sudo systemctl restart codedeploy-agent
```

# Create 2 Roles

1. Name: demo-ec2-to-s3-and-codedeploy
   - chose ec2 service
   - attatch below policies
       - AmazonEC2RoleforAWSCodeDeploy
       - AmazonS3FullAccess
   - Attach 1st role to All EC2 instances


2. Name: demo-code-deploy-to-other-services
   - chose codedeploy
   - attatch below policy
       - AWSCodeDeployRole

3. aws configure
  - Accesskey:
  - Secretkey
  - Region:us-east-1
  - JSON

4. CodeDeploy>>>>>>>Applications>>>>create Application>>>>Create deployment group

5. Goto Pipeline >>>> create pipeline.
```bash
less /var/log/aws/codedeploy-agent/codedeploy-agent.log
```
```bash
sudo systemctl restart codedeploy-agent
```
