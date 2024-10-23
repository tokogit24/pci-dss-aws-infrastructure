# pci-dss-aws-infrastructure

## Project Title: PCI-DSS Compliance Infrastructure on AWS

### Overview
This project sets up a PCI-DSS compliant infrastructure on AWS using Terraform. It includes a VPC, subnets, an Application Load Balancer (ALB), EC2 instances for the application and MySQL database, and security groups to manage traffic and access. This infrastructure is designed to address PCI-DSS requirements, specifically points 1.3.1 and 1.3.2.

# Terraform AWS Infrastructure

This repository contains a Terraform configuration to set up a PCI-DSS compliant AWS infrastructure.

## Summary

This repository contains a Terraform configuration for setting up a secure AWS infrastructure suitable for applications that handle sensitive data (PCI-DSS compliant). The configuration creates a VPC with public and private subnets, an Internet Gateway, a NAT Gateway, load balancers, security groups, and EC2 instances for an application and a database.

## Necessary Files

- **`main.tf`**: The primary Terraform configuration file containing all the resources.
- **`variables.tf`**: Defines the variables used in `main.tf`.
- **`outputs.tf`**: (Optional) Contains output values to display after deployment.
- **`README.md`**: Documentation explaining the project and how to use it.
- **`.gitignore`**: To ignore Terraform state files and other unnecessary files.

### Table of Contents
1. [Prerequisites](#prerequisites)
2. [Project Structure](#project-structure)
3. [Setup Instructions](#setup-instructions)
4. [Infrastructure Diagram](#infrastructure-diagram)
5. [License](#license)

### Prerequisites
- **AWS Account**: You need an active AWS account.
- **Terraform**: Install Terraform on your local machine. [Terraform Installation Guide](https://learn.hashicorp.com/tutorials/terraform/install-cli).
- **AWS CLI**: Optionally, install the AWS CLI for easier management. [AWS CLI Installation Guide](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html).
- **IAM Permissions**: Ensure your AWS user has permissions to create VPCs, EC2 instances, ALBs, and other related resources.

### Project Structure
```
terraform-aws-infrastructure/
│
├── main.tf              # Main Terraform configuration
├── variables.tf         # Variables definitions
├── outputs.tf           # (Optional) Output values
├── README.md            # Project documentation
└── .gitignore           # Git ignore file
```
### Setup Instructions

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/pci-dss-aws-infrastructure.git
   cd pci-dss-aws-infrastructure

2. ### Configure Terraform Variables

- Edit the `main.tf` file to replace placeholders with your actual values:
   - Replace `YOUR_TRUSTED_IPS` with the actual IP addresses that should have access.
   - Update the AMI ID in the `aws_instance` resource with a valid one for your region.
   - Set a secure password for the MySQL instance.
   - Update the variables in `variables.tf` with your desired values.

3. ### Run Terraform
   - Run `terraform init` to initialize the working directory, and to to download necessary providers and modules.
   - Run `terraform plan` to Generate and show an execution plan
   - Run `terraform apply` to deploy the infrastructure on AWS.
     
4. ### Verify the Deployment
- Once the deployment is complete, check the AWS Management Console.
- Note the ALB DNS name from the Terraform output.

5. ### Access the Application
Use the ALB DNS name to access the application via your browser.

6. ### Tear Down the Infrastructure.
   - Run `terraform destroy` If you need to remove the infrastructur

### Infrastructure Diagram
![image](https://github.com/user-attachments/assets/8d97913a-4f53-4b50-b069-7447850b7e67)

This diagram shows the basic structure of your infrastructure, with public subnets connected to the internet via the internet gateway, and private subnets accessing the internet through the nat gateway. the alb is placed in the public subnets to receive incoming traffic, while the application and database instances are in private subnets for enhanced security.

## License

This project is licensed under the MIT License.
