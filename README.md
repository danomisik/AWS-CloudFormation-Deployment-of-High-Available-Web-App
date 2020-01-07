

# Network configuration script
This script is for creation and configuration VPC. This script is from lesson from Carlos Rivas / Udacity
YAML = network.yml
PARAMETERS = network-params.json
## Quick Setup of Network
You can create it with:
aws cloudformation create-stack --stack-name udacity-deploy-web-app-env --template-body file://network.yml  --parameters file://network-params.json
You can update it with:
aws cloudformation update-stack --stack-name udacity-deploy-web-app-env --template-body file://network.yml  --parameters file://network-params.json

# Web Application Deployment
This script is for deployment of web application. This code is inspirated by Carlos Rivas / Udacity lessons.
YAML = deployWebApp.yml
PARAMETERS = deployWebApp-params.json
## Quick Deployment of High-available web app
You can create it with:
aws cloudformation create-stack --stack-name udacity-deploy-web-app --template-body file://deployWebApp.yml  --parameters file://deployWebApp-params.json --capabilities CAPABILITY_IAM
You can update it with:
aws cloudformation update-stack --stack-name udacity-deploy-web-app --template-body file://deployWebApp.yml  --parameters file://deployWebApp-params.json --capabilities CAPABILITY_IAM

        
Created by Daniel Misik