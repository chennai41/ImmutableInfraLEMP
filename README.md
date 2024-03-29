# LEMP Stack Immutable Infrastructure Using Packer, Ansible, and Terraform

We are going to use ansible code for provisioning static website using nginx during the baking process. We need to make sure nginx is enabled in systemctl and starts on every boot so it is ready to process on instance start. We are going assign tags in bake process to AMI. This tag is used by Terraform to identify the latest AMI available and use it for EC2 instance creation. We need to provide subnet id to packer builder so it can use this subnet id while creating AMI. We are going to divide our terraform code into two parts, one which contains all network details: create VPC, subnet, and other network details. Another part which spawns our EC2 instance inside our network using AMI generated by the packer.

## Getting Started

Step 1: Setup a network using Terraform

Step 2: Create AMI using packer and ansible inside the above-created network

Step 3: Setup EC2 instance inside the network with packer AMI

Provide access key and token in Terraform and Packer code.

### Command to run network Terraform

Go in folder networkTerraform, run command: 

1. terraform init

2. terraform plan

3. terraform apply

### Command to run Packer

Provide subnet id created in network terraform in packer.json

packer build packer.json

### Command to run main Terraform

Go in folder terraform, run command: 

1. terraform init

2. terraform plan

3. terraform apply
