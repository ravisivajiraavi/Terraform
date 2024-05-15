# VM Provisioning
## Deploying a VM in AWS Using the Terraform Workflow
## Additional Resources
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
    
### **Note: Please ensure that all resources are deployed in the AWS region us-east-1.**

### The Amazon Machine Image (AMI) ID and subnet ID has been placed in a file on the lab server called resource_ids.txt. You will access that file and copy/paste these values into your code to create your VM.

### To make sure the lab is fully provisioned, please wait an extra minute or two before connecting via ssh to the lab provided server.

    ssh cloud_user@<Terraform-Controller>
    
And, in a web browser, log in to the AWS Management Console using the credentials provided.
