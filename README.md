I created 2 Cloudformation Scripts:
1. Network configuration script
This script is for creation and configuration VPC. This script is from lesson from Carlos Rivas / Udacity
YAML = network.yml
PARAMETERS = network-params.json

You can create it with:
aws cloudformation create-stack --stack-name udacity-deploy-web-app-env --template-body file://network.yml  --parameters file://network-params.json
You can update it with:
aws cloudformation update-stack --stack-name udacity-deploy-web-app-env --template-body file://network.yml  --parameters file://network-params.json

2. Web Application Deployment
This script is for deployment of web application. This code is inspirated by Carlos Rivas / Udacity lessons.
YAML = deployWebApp.yml
PARAMETERS = deployWebApp-params.json

You can create it with:
aws cloudformation create-stack --stack-name udacity-deploy-web-app --template-body file://deployWebApp.yml  --parameters file://deployWebApp-params.json --capabilities CAPABILITY_IAM
You can update it with:
aws cloudformation update-stack --stack-name udacity-deploy-web-app --template-body file://deployWebApp.yml  --parameters file://deployWebApp-params.json --capabilities CAPABILITY_IAM

RUBRIC

Paramaters: A created few parameter for both scripts.
Resources: you can find all mentioned resources in deployWebApp script.
Ouputs: I created output with http + DNSName of Load Balancer.
WorkingTest: Application is working and you can find it on URL: http://udaci-WebAp-2KF9YI5441RV-421266270.eu-central-1.elb.amazonaws.com

TargetGroup: Associations Done.
Health Check and Listener: Healthy

Subnets: OK
Machine Specs: OK
SSH Key: Key name was replaced with Parameter Store parameter during setup. In production KeyName propert was deleted from LaunchConfiguration.

Output: DNS name of load balancer
Bastion Host: Not done, unfortunately.

Resume: Everything is done except Bastion server deployment.
        
Created by Daniel Misik