# pci-dss-aws-infrastructure

## Project Title: PCI-DSS Compliance Infrastructure on AWS

### Overview
This project sets up a PCI-DSS compliant infrastructure on AWS using Terraform. It includes a VPC, subnets, an Application Load Balancer (ALB), EC2 instances for the application and MySQL database, and security groups to manage traffic and access. This infrastructure is designed to address PCI-DSS requirements, specifically points 1.3.1 and 1.3.2.

### Table of Contents
1. [Prerequisites](#prerequisites)
2. [Project Structure](#project-structure)
3. [Setup Instructions](#setup-instructions)
4. [Infrastructure Diagram](#infrastructure-diagram)
5. [Discussion Points](#discussion-points)
6. [License](#license)

### Prerequisites
- **AWS Account**: You need an active AWS account.
- **Terraform**: Install Terraform on your local machine. [Terraform Installation Guide](https://learn.hashicorp.com/tutorials/terraform/install-cli).
- **AWS CLI**: Optionally, install the AWS CLI for easier management. [AWS CLI Installation Guide](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html).
- **IAM Permissions**: Ensure your AWS user has permissions to create VPCs, EC2 instances, ALBs, and other related resources.

### Project Structure

## Directory Structure  
/pci-dss-aws-infrastructure │ ├── main.tf # Terraform configuration file ├── variables.tf # Variables used in the Terraform configuration └── README.md # Project documentation

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

### Initialize Terraform, Plan the Infrastructure, Apply the Configuration, Tear Down the Infrastructure.
###Initialize Terraform to download necessary providers and modules:
```bash
terraform init

###Plan the Infrastructure
Generate and show an execution plan:
terraform plan

###Apply the Configuration
Deploy the infrastructure on AWS:
terraform apply

###Verify the Deployment
- Once the deployment is complete, check the AWS Management Console.
- Note the ALB DNS name from the Terraform output.

###Access the Application
Use the ALB DNS name to access the application via your browser.

###Tear Down the Infrastructure
If you need to remove the infrastructure, run:
terraform destroy
