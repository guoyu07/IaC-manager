### IaC: Manager Node
This terraform script will setup an infra for management in AWS:
 - CentOS (Manager Node)
 - VPC
 - Public subnet
 - Internet gateway

#### Pre-requisites
- An IAM account with administrator privileges.
- Install terraform in the machine: https://www.terraform.io/intro/getting-started/install.html

#### Steps for installation
- Clone this repo .
- Copy your AWS ssh key into current dir.
- `cp terraform.dummy terraform.tfvars`
- Modify params in `terraform.tfvars`
- Modify params in `variable.tf` to change subnet or add AMI accordingly to your aws region
- Run `terraform plan` to see the plan to execute.
- Run `terraform apply` to run the scripts.
- You may have `prod/dev/stage` configurations in
`terraform.tfvars.{prod/dev/stage}` files (already ignored by `.gitignore`).

#### Notes
SSH into the manager node and check whether `terraform.out` in `home/centos` contains:
a record of the VPC, Subnet, Security Group and Nat gateway ID.
