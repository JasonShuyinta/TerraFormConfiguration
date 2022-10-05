# TerraFormConfiguration

## learn-terraform-aws-instance
To start an AWS instance using Terraform as the Infrastructure As Code (IAC) tool, you need to create a file with the .tf extension, such as main.tf, 
and define a terraform block which contains the settings, including the required providers Terraform will use to provision your infrastructure.

Define the resource block to define the components of your infrastructure (such as an EC2 instance).
You first need to configure your AWS credentials with:
```
aws configure
AWS_ACCESS_KEY_ID = ....
AWS_SECRET_KEY = .....
```
After that you need to provide an AMI (Amazon Machine Image), which describes with an ID the type of instance and the region in which your instance will be hosted. 
In this case the AMI image is of a t2.micro instance (free tier) in the eu-centra-1 region.

#### Initialize
```
terraform init
```

#### Format and validate the configuration file
```
terraform fmt
terraform validate
```

#### Create the infrastructure
This will create your infrastructure on AWS. 
```
terraform apply
```

#### Inspect
The state of your infrastructure will be maintained in a file called terraform.tfstate.
N.B. Do not store this file on git.
```
terraform show
```

#### Destroy Infrastructure
```
terraform destroy
```

## learn-terraform-docker-container
This command downloads the necessary plugins to allow Terraform to interact with Docker.
(Docker Desktop needs to be running).
```
terraform init
```
Provision the NGINX server container with the apply command. 
```
terraform apply
```
Navigate to [localhost:8000](http://localhost:8000 "localhost") to visit the nginx server up and running.
You can even see the container running on Docker Desktop with its relative image.
