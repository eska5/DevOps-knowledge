#    Hashicorp Terraform Associate

-----
-----
-----

#    What you need to know about Infrastructure as Code

Provisioning infrastructure through `software` to achieve `consistent` and `predictable` deployments

###    Core Concepts
- Defined in  code
- Stored in source control
- Declarative or Imperative
- Idempotent and Consistent
- Push or Pull

###    Benefits of Infrastructure as a code
- Automated Deployment
- Repeatable process
- Consistent environments
- Reusable components
- Documented architecture


###    Deploying Your First Terraform Configuration

####    What is terraform
- Infrastructure automation tool
- Open-source and vendor agnostic
- Single binary compiled from go
- Declarative syntax
- HashiCorp Configuration Language or JSON
- Push based deployment

####    Core Components
- Executable
- Configuration files
- Provider plugins
- State data

####    Terraform object types
- Providers
- Resources
- Data sources

![](https://i.imgur.com/psq4yxE.png)
![](https://i.imgur.com/UQ4ns4d.png)

#####    if we want to get to name we should say: `aws_instance.web_server.name`

###    Terraform workflow
- terraform init
- terraform plan
- terraform apply
- terraform destroy
- terraform validate

#####    Can use `terraform plan -out xyz.tfplan`

#####    plan: A to add, B to change, C to destroy

###    Using Input variables and Outputs
- Input variables
- local values
- output values

![](https://i.imgur.com/PiSLqfb.png)
![](https://i.imgur.com/P3ykFii.png)

####    Data types
- Primitive
    - string
    - number
    - boolean
- Collection
    - List 
    - set
    - map
- Structural
    - Tuple
    - object

![](https://i.imgur.com/oBlMoEr.png)
![](https://i.imgur.com/RxTrHaG.png)
![](https://i.imgur.com/DYGjfTU.png)
![](https://i.imgur.com/LIZNkDL.png)

####    Supply variable Values
- Default value
- -var flag
- -var-file flag
- terraform.tfvars
- .auto.tfvars
- Environment variable TF_VAR_

#####    Evaluation Precedence
![](https://i.imgur.com/OjjeeFK.png)

###    Updating your configuration with more resources
- Improving our architecture
- Using the documentation
- Adding resources 
- Viewing state data

### Terraform State
- JSON format (Do not touch!)
- Resources mappings and metadata
- Locking
- Location
    - Local
    - Remote: AWS, Azure, NFS, Terraform Cloud
- Workspaces
![](https://i.imgur.com/9Rhj2iG.png)


####    State Commands
- terraform state list
- terraform state show ADDRESS
- terraform state mv SOURCE DESTINATION
- terraform state rm ADDRESS

###    Terraform Providers
- Public and private registries
    - Official
    - verified
    - Community
- Open Source and written in GO
- Resources and data sources
- Versioned
- Multiple instances
![](https://i.imgur.com/Hft8CLt.png)

###    Terraform Planning
- Refresh and inspect state
- Dependency graph
- Additions, updates, and deletions
- Parallel execution

####    Post Deployment Configuration
- Resource
- Pass data
- Config Manager
- Provisioners

#####    Provisioners
- Defined in resource
- Creation or destruction
- Multiple provisioners
- null_resource
- Failure options
- Last Resort!

###    PROVISIONES ARE LAST RESORT !!!




![](https://i.imgur.com/6VRyt8u.png)
![](https://i.imgur.com/D0UohBt.png)

###    `terraform fmt` formats code :)

##    Loops in Terrafom
- Count (Integer)
- for_each (Map or Set)
- Dynamic Blocks (Map or Set)

####    Count Syntax
![](https://i.imgur.com/KtFLwVx.png)

####    For_each Syntax
![](https://i.imgur.com/9oJlqUT.png)
![](https://i.imgur.com/WFpQFhK.png)


###    Terraform Functions And Expressions

####   Terraform Expressions
- Interpolation and heredoc
- Arithmetic and logical operators
- Conditional expressions
- For expressions

####    Terraform Functions
- built-in Terraform
- Func_name(arg1, arg2, ...)
- Test in terraform console
- Several broad categories

####   Common Function Categories
- Numeric min(77, 12)
- String lower("XYZ")
- Collection merge(map1, map2)
- IP network cidrsubnet
- Filesystem file(path)
- Type Conversion toset()


`${path.module}` is a path to a module in which we are :100: 

You can reference local in local !

###    Terraform modules
- Code reuse
- Remote or local source
- Versioning
- Terraform init
- Multiple instances

####    Module Components
- Input Variables
- Output Values
- Resources and Data Sources

####    Module Syntax
![](https://i.imgur.com/gJcRdjZ.png)


###    Multiple environments
- Commonality and differences
- Abstractions and reuse
- Production access


####    Multiple Environment Decisions
- State management
- Variable balues
- Credentials management
- Complexity and overhead

###    State file example
![](https://i.imgur.com/pczku7d.png)
![](https://i.imgur.com/HXFPIXh.png)

---
---
---

#    TERRAFORM DEEP DIVE

###    Terraform Cloud
- SaaS Offering
- Remote state
- Remote execution
- Variable and secret storage
- Source control integration


---
---
---

#    Example Questions

###    Contents

- Understand infrastructure as code (IaC) concepts
- Understand Terraform’s purpose (vs other IaC)
- Understand Terraform basics
- Use the Terraform CLI (outside of core workflow)
- Interact with Terraform modules
- Navigate Terraform workflow
- Implement and maintain state
- Read, generate, and modify the configuration
- Understand Terraform Cloud and Enterprise capabilities


##    Understand infrastructure as code (IaC) concepts

####    What are the advantages of terraform
- Platform Agnostic
- State Management
- Operator Confidence

##    Understand Terraform’s purpose (vs other IaC)

####    What is multi-cloud deployment?
``` Provisoning your infrastrcutire into multiple cloud providers to increase fault-tolerance of your applications.```

#    USEFUL LINK WITH 250 EXAMPLE QUESTIONS:
###    https://medium.com/bb-tutorials-and-thoughts/250-practice-questions-for-terraform-associate-certification-7a3ccebe6a1a

