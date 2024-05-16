# **VM Provisioning**
## **Deploying a VM in AWS Using the Terraform Workflow**
## **Additional Resources**
### To create your EC2 instance (VM) in AWS, use the code provided below:

    provider "aws" {
      region = "us-east-1"
    }
    resource "aws_instance" "vm" {
      ami           = "DUMMY_VALUE_AMI_ID"
      subnet_id     = "DUMMY_VALUE_SUBNET_ID"
      instance_type = "t3.micro"
      tags = {
        Name = "my-first-tf-node"
      }
    }
    
### **Note: Please ensure that all resources are deployed in the AWS region us-east-1**

#### The Amazon Machine Image (AMI) ID and subnet ID has been placed in a file on the lab server called resource_ids.txt. You will access that file and copy/paste these values into your code to create your VM

#### To make sure the lab is fully provisioned, please wait an extra minute or two before connecting via ssh to the lab provided server

    ssh cloud_user@<Terraform-Controller>
    
#### And, in a web browser, log in to the AWS Management Console using the credentials provided

### **Description**
#### In this hands-on lab, we will be following the Terraform workflow — Write > Plan > Apply — to deploy a virtual machine (VM) in AWS. After a successful deployment, we will then clean up our infrastructure and destroy the resource we created

### **Objectives**
#### Successfully complete this lab by achieving the following learning objectives:

1. Create a Directory and Write Your Terraform Code (Write)
    - Create a new directory in the cloud_user's home directory to house your Terraform code called terraform_code
    - Create a new file for your code called main.tf
    - Add the provided code for creating your VM (as an EC2 instance in AWS) to the main.tf file
2. Plug the Provided AMI and Subnet ID Values Into Your Code
    - Copy the AMI and subnet ID for the VM that have been saved in the resource_ids.txt file on the lab server
    - Paste these values into your code in the main.tf file
3. Initialize and Review Your Terraform Code (Plan)
    - Initialize your Terraform configuration with the terraform init command.
    - Review the actions that will be performed when code is deployed using the terraform plan command.
    - Deploy Your Terraform Code (Apply), Verify Your Resources, and Clean Up
4. Deploy the code with the terraform apply command.
    - Verify that your resource was created as intended in the AWS Management Console.
    - Tear down the infrastructure using the terraform destroy command.
    - Verify that your resource was destroyed and removed in the AWS Management Console.
