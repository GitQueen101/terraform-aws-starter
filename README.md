# terraform-aws-starter

AWS VPC, EC2, and S3 provisioned with modular Terraform.

![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat&logo=terraform&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat&logo=amazon-aws&logoColor=white)

## Overview

Infrastructure as Code (IaC) project using Terraform to provision a complete AWS environment. Uses modular structure, remote state, and variable files following real-world Terraform best practices.

## Infrastructure Provisioned

- VPC with public and private subnets
- EC2 instance (Amazon Linux 2, t2.micro - free tier)
- S3 bucket with versioning enabled
- Security groups with least-privilege rules
- IAM roles and policies

## Tech Stack

- Terraform 1.x
- AWS (EC2, VPC, S3, IAM)
- S3 remote state backend
- tfvars for environment-specific config

## Project Structure

```
terraform-aws-starter/
├── modules/
│   ├── vpc/
│   ├── ec2/
│   └── s3/
├── environments/
│   └── dev/
│       ├── main.tf
│       ├── variables.tf
│       ├── outputs.tf
│       └── terraform.tfvars
├── backend.tf
└── README.md
```

## Usage

```bash
terraform init
terraform plan -var-file="environments/dev/terraform.tfvars"
terraform apply -var-file="environments/dev/terraform.tfvars"
terraform destroy
```

Always run `terraform destroy` after testing to stay in the AWS free tier.

---

Part of the [GitQueen101 DevOps portfolio](https://github.com/GitQueen101).
