# Cloud_application

This Terraform code deploys the following resources:

- An S3 bucket
- A Lambda function with an execution role
- An API Gateway REST API with a resource, method, and integration to the Lambda function
- A Cognito User Pool, Client, and Identity Pool for Single Sign-On (SSO)

The resources are connected as follows:

- The Lambda function is triggered by the API Gateway integration
- The API Gateway REST API is secured by the Cognito User Pool and Client
- The Cognito Identity Pool is used to authenticate users for the API Gateway

To run the code:

1. Install Terraform and AWS CLI on your machine
2. Create a new directory for your Terraform project and navigate into it
3. Copy the main.tf and sso.tf files into the directory
4. Create a new file named lambda.zip containing your Lambda function code (in this case, the index.js file)
5. Initialize the Terraform working directory by running terraform init
6. Apply the Terraform configuration by running terraform apply
7. Enter yes when prompted to confirm the deployment
