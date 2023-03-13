#    Terraform

INFRASTRUCTURE AS CODE - Provisioning infrastructure through software to achieve consistency and predictable deployment

* Defined in code
* Stored in source control
* Declarative(already has idea what to do example:struct 

taco{x: x, y: y}

or imperative(exact commands, step by step)

* Idempotent(has knowledge about the environment) and consistent
* Push and pull

 

### BENEFITS
* Automated deployment
* Repeatable process
* Consistent environments
* Reusable components
* Documented architecture

TERRAFORM - a tool to automate the deployment and management of infrastructure
core - single binary compiled from go

declarative syntax

config files are written in json or hashicorp config language

Push based deployment

###   CORE COMPONENTS
* Executable
* Configuration files
* Provider plugins
* State data

###    COMMANDS:
![](https://i.imgur.com/23CoLmt.png)

###    TERRAFORM OBJECT TYPES:
* Providers - information about the provider
* Resources - things I want to create in environment
* Data sources - way to store information

### Block Syntax:

  
``` terraform
Block_type "label" "name_label" {
	Key = "value"
	Nested_block {
		Key = "value"
	}
}
```
Example:
``` terraform
Resource "aws_instance" "web_server" {
	Name = "web-server"
	Ebs_volume {
	Size = 40
	}
}
```

###    Get the resource:

Aws\_instance.web\_server.name

``` terraform
Provider "aws" {
	access_key = "ACCESS_KEY"
	secret_key = "SECRET_KEY"
	region = "us-east-1"
}

Data "aws_ssm_parameter" "ami" {
	Name = "xyz"
}
```

###    USING INPUT VARIABLES AND OUTPUT

* Input variables - used to pass information to a terraform configuration
* Local values - computed inside configuration
* Output values - defined in the configuration

###    INPUT VARIABLES:

``` terraform
Variable "name_label" {
	Type = value
	Description = "value"
	Default = "value"
	Sensitive = true|false
}
```

Example:

``` terraform
Variable "billing_tag"{}
Variable "aws_region"{
	Type = string
	Description = "Region to use foraws resource"
	Default = "us-east-1"
}
```
Reference : `var.aws_region`

###    TERRAFORM DATATYPES
* String, number, boolean
* List, set, map
* Tuple, object

###    LOCALS

Example:

``` terraform
Locals{
	Common_tags = {
	Company = var.company
	Project = "${var.company}-${var.project}"
	Billing_code = var.billing_code
	}
}
```

In `main.tf` :

``` terraform
tags = local.common_tags in resources brackets
```

###    OUTPUTS

Example:
``` terraform
output "aws_instance_public_dns" {
	Value = aws_instance.nginx1.public_dns
}
```

###    TO VALIDATE
``` bash 
terraform init
terraform validate
```

###    SUPPLY VARIABLE VALUES

default value
-var flag
-var-file flag
Terraform.tfvars.json
.auto.tfvars.json
Environment variable TF\_VAR\_


