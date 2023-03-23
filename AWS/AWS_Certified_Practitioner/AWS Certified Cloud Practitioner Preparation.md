#    AWS Certified Cloud Practitioner Preparation

###    Understanding Cloud Computing

Cons that cloud computing solves:
- Large up-front investmenrs
- Forecasting demand is difficult
- slow to deploy new data centers
- maintaining data servers
- security maintenance

Pros:
- variable expense
- benefits from massive economies of scale
- don't have to guess capacity
- increase speed and agility
- stop spending money maintaining data centers
- going global in minutes

---
* `ELASTICITY` - Ability to acquire resources as you need them and release when you no longer need them.
* `RELIABILITY`
* `AGILITY`
* `PAY-AS-YOU-GO`

---
####    Cloud Computing Models
![](https://i.imgur.com/j94WKVp.png)

* Public Cloud
* On-Premises Private Cloud
* Hybrid

###    AWS Global Infrastructure

####    AWS Regions and Availability Zones

- specific location
- 30 launched regions
- one or more data centers
- multiple availability zones in each AWS region
- Redundant power, networking and connectivity
- approx 96 availability zones

---
- `AVAILABILITY`

#####    Naming

example: `us-east-2a`
![](https://i.imgur.com/pvijEWV.png)

---

- Local Zones
- wavelength zones

#####    AWS Edge Locations

`Points of Presence`
- 410 points of presence
- 400 edge locations
- 13 regional edge caches

Significance:
- Used as nodes of a global content delivery network (CDN)
- Utilized by Amazon CloudFront and Amazon Route 53
- Allows AWS to serve content from locations closest to users


###    Understanding Cloud Economics

`Capitalized Expenditure`
`Operating Expenditure`

######    Own data center
![](https://i.imgur.com/8Q22zCv.png)

######    Cloud
![](https://i.imgur.com/RazqTFg.png)

######    Pros and Cons
![](https://i.imgur.com/F6sMWTA.jpg)

#####    AWS Cost Explorer
`Cost explorer`
- Exploring AWS costs
- Prediction for the next 3 months
- gives recommendation for cost optimization
- breakdowns by service or cost tag

`AWS Budgets` - utilizes data to track and plan usage across AWS services

####     AWS Cost Planning Tools
- `AWS Pricing Calculator`
- `AWS Migration Hub`
####    AWS Resource Tags
- Metadata assigned to a specific AWS resource
- Includes a name and an optional value
- Common use cases include department, environment, or project
- Cost allocation report includes costs grouped by active tags

####    AWS ORGANIZATIONS
- Allows organizations to manage multiple accounts under a single master account
- Provides organizations with the ability to leverage Consolidated Billing for all accounts
- Enable organizations to centralize logging and security.

####    Building a Business Case
- Analyze the current workloads
- Forecast infrastructure needs
- Create a TCO analysis of both options

Tools:
- AWS MIGRATION HUB
- MIGRATION EVALUATOR

###    Supporting AWS Infrastructure 

AWS Support 
- Enables support from AWS resources for workloads running in the cloud
- Provided in different tiers based on need and scope
- Includes tools to provide automated answers and recommendations

AWS Personal Health Dashboard

AWS Trusted Advisor checks:
- Cost Optimization
- Performance
- Security
- Fault Tolerance
- Service Limits

#####    AWS Support Plan Tiers

Differences:
- Communication method
- Response Time
- Cost
- Type of guidance offered

AWS Basic support
- Provided for all customers
- Access to Trusted Advisor
- 24x7 Access to customer service, documentation, forums
- Access to AWS Personal Health dashboard
- no monthly cost

AWS Developer Support
- Includes all features of Basic Support
- Business hours email access to support engineers
- Limited to 1 primary contact
- Starts at 29$ per month

AWS Business Support
- Includes All features of Developer Support
- Full set of Trusted Advisor checks
- 24x7 phone, email, and chat access to support engineers
- Unlimited contacts
- Provides third-party software support
- Starts at 100$ per moth

AWS Enterprise Support
- Includes all features of Business Support
- Includes designated Technical Account Manager (TAM)
- Includes concierge support team
- Starts at 15.000$ per month

#####    Support Response Times



|          | Developer     | Business | Enterprise |
| -------- | -------- | -------- | -------- | 
| General Guidance     | 24 business hours     | 24 hours | 24 hours | 
| System Impaired     | 12 business hours     | 12 hours | 12 hours | 
| Production System Impaired     |      | 4 hours | 4 hours | 
| Production System Down     |      | 1 hours | 1 hours | 
| Business-Critical System down     |      |  | 15 minutes | 


![](https://i.imgur.com/lLE2EWg.png)



---
---
---



#    Understanding AWS Core Services

###    Interacting with AWS

- AWS Console
A web application for interacting with services
- AWS CLI
Command line tool. Can do same things that can be done in AWS Console
- AWS SDK
Used in programming language for example go. Enables automation.

console is great for testing
repeated tasks should be automated with CLI or SDK
custom application should use SDK

####    AWS Console

Difference between signing as Root user and IAM user
root user is main user (admin account) for stuff like deleting account

`Route53 does not need to select region`

####    AWS CLI
account name -> security credential

authentication:
- MFA
- Access keys (best for IAM users)

Available for:
- Windows
- Linux
- Mac

AWS CloudShell is an online option.

##    Compute Services

###   AMAZON EC2 

When can we use it?
- Web application hosting
- Batch processing
- Web services endpoint
- Desktop in the cloud

Concepts
- Instance Types
- Root Device Types
- Amazon Machine Image (AMI)
- Purchase Options

#####    EC2 Instance Types
- Defines the processor, memory, and storage type
- Cannot be changed without downtime
- Provided in the following categories
    - general purpose
    - Compute, memory, and storage optimized
    - Accelerated computing
- Pricing is based on instance type
- Some instance types have unique capabilites

![](https://i.imgur.com/jcovUS4.png)

#####    Root Device Types
- Instance Store
    - [Physically attached to the host] 
    - ephemeral
- Elastic Block Store (EBS) 
    - [Persistance storage that exists separate from the host]
    - persistent

#####    Amazon Machine Image (AMI)
- Template for an EC2 instance including configuration, operating system, data
- AWS provides many AMI's that can be leveraged
- AMI's can be shared across AWS accounts
- Custom AMI's can be created based on your configuration
- Commercial AMI's

###    EC2 Purchase Types
- On-Demand
- Reserved
    - Provides discounts over the on-demand model for a declaration to be using it for a period of time
        - Standard (Highest Discount)
        - Convertible (Convert attributes)
        - Scheduled (time window)
    -    Reserved Instance Cost Models
            - All Upfront (Maximum Savings)
            - Partial Upfront
            - No Upfront (Minimum Upfront Const)  
- Savings Plan
    - Similar in ceoncept to reserved instances
    - Supports compute with EC2, Fargate, and Lambda
    - Unlike Reserved Instances, it does not reserve capacity
    - Provide savings of up to 72%
    - Comes in 1 or 3 year terms
- Spot
    - Can provide up to 90% discount on-demand pricing
    - There is a market price for instance types per availability zone called the Spot price
    - When you request instances, if your bid is higher than Spot price they will launch
    - If the Spot price grows to exceed your bid, the instances will be terminated
    - Spot instances can be notified 2 minutes prior to termination
- Dedicated (If you have to for example hold government data within the country territory)

1. Consistent and always needed Instance - `Standard` or `Convertible Reserved`
2. Batch processing when process can start and stop - `Spot Instances`
3. Inconsistent need - `On-Demand`
4. Compliance requiremend - `Dedicated host`

## Standard
![](https://i.imgur.com/sIjYMOj.png)

##    SPOT
![](https://i.imgur.com/JSJKdmw.png)

##    AWS Elastic Beanstalk
####    Why
- Automates the process of deploying and scaling workloads on EC2 (PaaS)
- Supports a specific set of technologies
- Leverages existing AWS services
- Only pay for the other services you leverage
- Handles provisioning, load balancing, scaling, and monitoring

####    Features
- Monitoring
- Deployment
- Scaling
- EC2 Customization

#### Use cases
- Deploy an application with minimal knowledge of other servies
- Reduce the overall maintenance needed for the application
- Few customizations are required


##    AWS Lambda
AWS Lambda lets you run code without provisioning or managing servers. Paying for the compute time you consume. Run Code for any type of application - with zero administration

- Enables the running of code without provisioning infrastructure
- Only charged for usage based on execution time
- Can configure available memory from 128MB to 3008MB
- Integrates with many AWS Services
- Enables event-driven workflows
- Primary service for serverless approach

#####    Advantages
- Reduced maintenance requirements
- Enables fault tolerance without additional work
- Scales based on demand
- Pricing is based on usage

##    Container Services

AWS App Runner - deploy containers without prior knowledge

#####    Container Orchestration SErvices

- Amazon ECS - Full featured container orchestration service
- Amazon EKS - Kubernetes based full-featured container orchestration service

#####    Compute Engines

- Amazon EC2
- AWS Fargate - Serverless compute engine for use with the container orchestration service (scaling)

#####    Selecting a Container Service
- App Runner requires no prerequisite knowledge of containers or infrastructure
- EKS will provide an easier starting point for Kubernetes in the cloud
- ECS natively integrates with many AWS services
- Fargate reduces the amount you have manage for container orchestration
- EC2 provides maximum control for configuration of scaling with containers

#    Content and Network Delivery Services
- Amazon Route 53
- Amazon VPC
- AWS Direct Connect
- Amazon API Gateway
- Amazon CloudFront
- Elastic Load Balancing

## Amazon VPC and Direct Connect
VPC - Virtual Private Cloud - isolated section of the AWS Cloud for AWS Resources

### Amazon VPC
- Enables virtual network in AWS
- Supports IPv4 and IPv6
- Allows for configuration of
    - IP address range
    - Subnets
    - Route tables
    - Network gateways
- Supports public & private subnets
- Can utilize NAT for private subnets
- Enables a connection to your data center
- Can connect to other VPC's
- Supports private connections to many AWS services

### AWS Direct Connect 
Establish a dedicated network connection from your data center to AWS

## Amazon Route 53
- Domain name service (DNS)
- Global AWS service
- Highly available
- Enables global resource routing

## Elastic Load Balancing
- Distribute traffic across multiple targets
- Integrates with EC2, ECS, and Lambda
- Supports one or more AZ's in a region
- Three types of load balancers:
    - Application Load Balancer (ALB)
    - Network Load Balancer (NLB)
    - Classic Load Balancer (ELB)

###    Scaling
- Vertical Scaling - scaling up (adding resources and moving to a larger instances)
- Horizontal Scaling - scaling out (adding additional instances)

## Amazon CloudFront and API Gateway

###    Amazon CloudFront
- Content delivery network (CDN)
- Enables users to get content from server closest to them
- Supports static and dynamic content
- Utilizes AWS edge locations
- Includes Advanced security features:
    - AWS Shield for DDoS
    - AWS WAF

###    Amazon API Gateway
- Fully managed API management services
- Directly integrates with multiple AWS servives
- Provides monitoring & metrics on API calls
- Supports VPC and on-premise private applications

## AWS Global Accelerator
- Utilizes IP addresses that route to edge locations
- Once request reaches edge locations, traffic is routed through AWS network
- Can route requests to many AWS resoureces:
    - Network Load Balancer (NLB)
    - Application Load Balancer (ALB)
    - EC2 Intances
    - Elastic IP address

###    Performance improvements
- Distance between user and initial endpoint is minimized by using edge locations
- Traffic is optimized by using AWS network instead of public internet
- Results in improvements of first byte latency, jitter, and throughput
- Provides superior fault tolerance by not relying on DNS resolution

### Use cases
- non HTTP Protocol (UDP, MQTT, VOIP)
- Requires Static IP
- Instant Failover

#    File Storage Services
- Amazon S3
- Amazon S3 Glaciar
- Amazon Elastic Block Store (EBS)
- Amazon Elastic File System (EFS)
- AWS Snowball
- AWS Snowmobile

###    Amazon S3
- Stores files a objects in buckets
- Provides different storage classes for different use cases
- stores data across multiple availability zones
- Enables URL access for files
- Offers configurable rules for data lifecycles 
- Can serve as a static website host

####    Non-archival Storage Classes
- S3 Standard
- S3 Intelligent Tiering
    - Automatically moves files based on access
    - Moves between frequent and infrequent access
    - Same performance as S3-Standard
- S3 Standard-IA
- S3 One Zone-IA

####    S3 Lifecycle Policies
- Objects in a bucket can transition or expire based on your criteria
- Transitions can enable objects to move to another storage class based on time
- Expiration can delete objects based on age
- Policies can also factor in versions of a specific object in the bucket

`S3 Transfer Acceleration`

###    Amazon S3 Glacier
- S3 Glacier Instant Retrieval
- S3 Glacier Flexible Retrieval
- S3 Glacier Deep Archive

####    Retrieval Times
- Instant Retrieval can be retrieved in milliseconds
- Flexible Retrieval can have configurable retrieval times from minutes to hours
- Deep Archive has a retrieval time withing 12 hours

####    Use Cases
- AWS recommends Instant Retrieval for medical images, news media
- AWS recommends Flexible Retrieval for backup or disaster recovery
- AWS recommends Deep Archive for long-term data storage to meet compliance requirements or cases where the lowest cost is critical

###    Elastic Block Store (EBS)
- Enables redundancy within an AZ
- Allows users to take snapshots of its data
- Offers Encryption of its volumes
- Provides multiple volume types:
    - General purpose SSD (standard)
    - Provisioned IOPS SSD (high performance)
    - Throughput optimized HDD (frequent data access)
    - Cold HDD (less frequent access workload)

###    Elastic File System (EFS)
- Fully managed NFS file system
- Designed for Linux workloads
- Supports up to petabyte scale
- Stores data across multiple AZ's
- Provides two different storage classes:
    - Standard
    - Infrequent access
- Provides configurable lifecycle data rules


###    Data Transfer with AWS Snowball
- AWS Snowball
    - Supports petabyte scale transfer
    - Physical device is delivered by AWS
    - AWS receives device and loads your data into S3
- AWS Snowmobile
    - Supports exabyte scale
    - Shipping container is delivered to your location
    - AWS sets up a connection to your network 
    - You load your data on the Snowmobile
    - AWS will load data into S3 when the container is received at an AWS location


# Database Services and Utilities
- Amazon RDS
- Amazon Aurora
- Amazon DynamoDB
- Amazon Redshift
- Amazon Elasticache
- AWS Database Migration Service

###    Amazon Relational Database Service (RDS)
- Fully managed service for relational database
- Handles provisioning, patching, backup, and recovery of your database
- Supports deployment across multiple availability zones (multi-AZ)
- Some platforms support read replicas
- launches into a VPC
- Provides both general purpose SSD and provisioned IOPS SSD drive options

####    Amazon RDS Platforms
- MySQL
- PostgreSQL
- MariaDB
- Oracle Database
- SQL Server
- Amazon Aurora

`Amazon Database Migration Service (DMS)`

###    Amazon DynamoDB
- Fully managed NoSQL database service
- Provides both key-value and document database
- Enables extremely low latency at virtually any scale
- Supports automated scaling based on configuration
- Offers in-memory cache with the DynamoDB

####    DynamoDB Use Cases
- Scale without excessive maintenance
- Serverless applications
- Implementations where low latency is key
- Data models without BLOB storage

###    Amazon Elasticache & Redshift
####    Amazon Elasticache
- Fully managed in-memory data stores
- Supports both Memcached and Redis
- Provides low latency in response times
- Enables scaling and replicas to meet application demand
- Handles common use cases including:
    - Database layer caching
    - Session storage

####    Amazon Redshift
- Scalable data warehouse service
- Supports petabyte scale warehousing of data
- Leverages high performance disks and columnar storage
- Offers the ability to fully encrypt contents
- Provides isolation with a VPC
- Enables querying of exabytes of data in Amazon S3 using Redshift Spectrum

###    Additional Database Services
- DocumentDB
    - Organizations running some MongoDB workloads on AWS
- Neptune
    - mapping relationships between data points
- MemoryDB for Redis
    - a fast in-memory primary database
- Timestream
    - storing and retrieving time series data points

#    AWS App Integration Services

## Amazon SNS (Simple Notification Service)
- Fully managed pub/sub messaging service
- Enables you to create decoupled applications
- Organized according to topics
- Integrates with multiple AWS services
- Provides end user notifications across SMS, email, and push notifications

## Amazon SQS
- Fully managed message queue service
- Enables you to build decoupled and fault tolerant applications
- Supports up to 256 KB data payload
- Allows messages to be stored up to 14 days
- Provides two types of queues
    - Standard queue
    - FIFO Queue

## AWS Step Functions
- Enables orchestration of workflows through a fully managed service
- Supports serverless architectures
- Can support complex workflows including error handling
- Charged per state transition along with the other AWS services leveraged
- Workflows are defined using Amazon States Language

#    Management and Governance Services

##    AWS CloudTrail
- Inserts audit trail in an S3 bucket or into CloudWatch Logs
- Logs events in the regions in which they occur
- Meets many compliance requirements for infrastructure auditing
- As a best practice, it should be enabled on every AWS account
- Can be consolidated into an organizational trail using AWS Organizations

###    Use Cases
- Compliance requirement
- Forensic Analysis
- Operational Analysis
- Troubleshooting

##    Amazon CloudWatch
- Monitoring and management service
- Collects logs, metrics, and events from most AWS services
- Enables alarms based on metrics
- Provides visualization capabilites for metrics
- Allows for custom dashboards based on collected metrics

##    AWS Config
- Provides configuration history for infrastructure
- Works against rules that you can customize or even create custom validations
- Includes conformance packs for compliance standards including PCI-DSS
- Can work with AWS Organizations for both cross-region and cross-account setup
- Provides remediation steps for infrastructure not meeting criteria

##    AWS Systems Manager
- Provides multiple tools that make it easier to manage your AWS infrastructure
- Enables automation tasks for common maintenance actions
- Gives a secure way to access servers using only AWS credentials
- Stores commonly used parameters securely for operational use

##    AWS CloudFormation
- Managed service for provisioning infrastructure based on templates
- No additional charge
- Templates can be YAML or JSON
- Enables infrastructure as code
- Manages dependencies between resources
- Provides drift detection to find changes in your infrastructure

##    AWS OpsWorks
- Configuration management service
- Provides managed instances of Chef and Puppet
- Configuration is defined as code for servers
- Chet and Puppet manage the lifecycle of those configuration changes with services
- Works in a hybris cloud architecture for both cloud-based on on-premise servers

###    Subservices
- AWS OpsWorks for Chef Automate
- AWS OpsWorks for Puppet Enterprise
- AWS OpsWorks Stacks

##    AWS Organizations and Control tower
###    AWS Organizations
- Allows organizations to manage multiple accounts under a single master account
- Provides organizations with the ability to leverage Consolidated Billing for all accounts
- Enables organizations to centralize logging and security standards across accounts

###    AWS Control Tower
- Centralizes users across all AWS accounts
- Provides a way to create new AWS accounts based on templates
- Integrates Guardrails for accounts
- Includes a dashboard to gain operational insights from a single view

---
---
---

#    Introduction to Security and Architecture on AWS

##    AWS Architecture Core Concepts

###    `Unacceptable Use Policy`
- Sending unsolicited mass emails is prohibited
- Hosting or distributing harmful content is prohibited
- Penetration tests were not allowed but now they are for a specific services

`Least Privilege Access`

###    Shared Responsibility Model

AWS Responsibility - `Security of the cloud`
- Access and training for Amazon employees
- Global data centers and underlying network
- Hardware for global infrastructure
- Configuration management for infrastructure
- Patching cloud infrastructure and services

Customer Responsibility - `Security in the cloud`
- Individual access to cloud resources and training
- Data security and encryption
- Operating system, network, and firewall configuration
- All code deployed onto cloud infrastructure
- Patching guesting operating system and custom applications

###    AWS Well-architected Framework
- Operational Excellence
- Security
- Reliability
- Performance Efficiency
- Cost Optimization
- Sustainability

###   High-availability and Fault Tolerance
`Everything fails all the time`

Reliability on AWS:
- Fault Tolerance
- High Availability

Building Solutions on AWS
- Most managed AWS services provide high-availability out of the box
- When building solutions directly on EC2 fault tolerance must be architected
- Multiple availability zones should be leveraged
- Some services can enable fault tolerance in your custom applications
    - Simple Queue Service (SQS)
    - Route 53

###    Compliance

####    Common compliance Sstandards
- PCI-DSS: Compliance standard for processing credit cards
- HIPAA: Compliance standard for healthcare data
- SOC1,SOC2,SOC3: Third-party reviews of operational processes
- FedRAMP: Standard for U.S. government data handling
- ISO 27018: Standard for handling Personally Identifiable Info

####    Acceptable Use Policy
- AWS Config
- AWS Artifact
- Amazon GuardDuty

##    AWS Identities and User Management
`Least Privilege Access`

###    AWS Identity and Access Management (IAM)
- Service that controls access to AWS resources
- Using the service is free
- Manages both authentication and authorization
- Supports identity federation through SAML providers including Active Directory

###    AWS IAM Identities
- Users
- Groups
- Roles

###    Policies in AWS IAM
- A JSON document that defines permissions for an AWS IAM identity (principal)
- Defines Both the AWS services that the identity can access and what actions can be taken on that service
- Can be either customer managed or managed by AWS

###    AWS IAM Best Practices
- Multi-Factor Authentication
- Least Privilege Access

###     Amazon Cognito
- User directory service for custiom applications
- Provides UI components for many platforms
- Provides security capabilities to control account access
- Enables controlled access to AWS resources
- Can work with social and enterprise identity providers

###    Amazon Cognito Identity Providers
- Google
- Amazon
- Facebook
- Microsoft active directory
- SAML 2.0 Providers

##    Data Architecture on AWS

###    On-premise Data Integration Service
- AWS Storage Gateway
    - Integrates cloud storage into your local network
    - Deployed as a VM or specific hardware appliance
    - Integrates with S3 and EBS
    - Supports three different gateway types
        - Tape Gateway
        - Volume Gateway
        - File Gateway
- AWS DataSync
    - Leverages the DataSync agent deployed as a VM on your network
    - Integrates with S3, Efs, and FSx for Windows File Server on AWS
    - Greatly improved speed of transfer due to custom protocol and optimizations
    - Charged per GB of data transferred

###    Processing Data
- AWS Glue (ETL Service)
    - Fully managed ETL service on AWS
    - Supports data in Amazon RDS, DynamoDB, Redshift, and S3
    - Supports a serverless model of execution
- AWS EMR (Big-data cloud processing)
    - Enables big-data processing on Amazon EC2
    - Supports popular open-source frameworks and tools
    - Operates in a clustered environment without additional configuration
    - Supports many different big-data use cases
        - Apache Spark
        - Apache Hive
        - Apache HBase
        - Apache Flink
        - Apache Hudi
        - Presto
- AWS Data Pipeline (Data workflow orchestration)
    - Managed ETL service on AWS
    - Manages data workflow through AWS services
    - Supports S3, EMR, Redshift, DynamoDB, and RDS
    - Can integrate on-premise data stores

###    Analyzing Data
- Amazon Athena (query data stored in Amazon S3)
    - Fully-managed serverless service
    - Enables querying of large-scale data stored within Amazon S3
    - Queries are written using standard SQL
    - Charged based on data scanned for query
- Amazon Quicksight (Business Intelligence[dashboards])
    - Fully managed BI service
    - Enables dynamic data dashboard based on data stored in AWS
    - Charged on a per-user and per-session pricing
    - Multiple versions provided based on needs
- Amazon CloudSearch (Managed search for custom apps)
    - Fully managed search service on AWS
    - Supports scaling of search infrastructure to meet demand
    - Charged per hour and instance type of search infrastructure
    - Enables developers to integrate search into custom applications

###   Integrating AI and Machine Learning
- Amazon Rekognition (Computer vision)
    - Fully managed image and video recognition deep learning service
    - Identifies objects in images
    - Identifies objects and actions in videos
    - Can detect specific people using facial analysis
    - Supports custom labels for your business objects
- Amazon Translate (Translate text)
    - Fully managed service for translation of text
    - Currently supports 54 languages
    - Can perform language identification
    - Works both in batch and real-time
- Amazon Transcribe (Speach to text)
    - Fully-managed speech recognition services
    - Recorded speech is converted into text in custom applications
    - Includes a specific sub-service for medical use
    - Supports Batch and real-time transcription
    - Currently supports 31 languages

##    Disaster Recovery on AWS

###    Disaster Recovery Architectures
####    Options
- Backup and restore
    - Production data is backed up into Amazon S3
    - Data can be stored in either standard or archival storage classes
    - EBS data can be stored as snapshots in Amazon S3 also
    - In a Disaster Recovery event, a process is started to launch new environment
    - This approach has the  longest recovery time
    - Least cost
- Pilot Light
    - Key infrastructure components are kept running in the cloud
    - Designed to reduce recovery time over the Backup and Restore approach
    - Does incur cost of this infrastructure continually running in the cloud
    - AMI's are prepared for additional systems and can be launched quickly
- Warm Standby
    - A scaled-down version of the full environment is running in the cloud
    - Critical systems can be running on less capable instance types
    - Instance types and other systems can be ramped up for disaster recovery event
    - Does incur cost of this infrastructure continually running in the cloud
- Multi site
    - Full environment is running in the cloud at all times
    - Utilizes instance types needed for production not just recovery
    - Provides a near seamless recovery process
    - Incurs the most cost over the other approaches

###    Selecting a Disaster Recovery Architecture
- Recovery Time Objective (RTO)
- Recovery Point Objective (RPO)

##    Architecting Applications on Amazon 

###    Scaling EC2 Infrastructure
- Vertical Scaling
- Horizontal Scaling (Easier in the cloud)


####    Amazon EC2 Horizontal Scaling Services
- Auto-scaling Group
    - Launch template defines the instance configuration for the group
    - Define the minimum, maximum, and desired number of instances
    - Performs health checks on each instance
    - Exists within 1 or more availability zones in a single region
    - Works with on-demand and spot instances
- Elastic load Balancer

####    AWS Secret Manager
- Secure way to integrate credentials, API keys, tokens, and other secret content
- Integrates natively with RDS, DocumentDB and Redshift
- Can auto-rotate credentials with integrated services
- Enables fine-grained access control to secrets

###    Controlling Access to EC2 Instances

####    Security in Amazon VPC
- Security groups
    - Serve as a firewall for your EC2 instances
    - Control inbound and outbound traffic
    - Works at the instance level
    - EC2 instances can belong to miltiple security groups
    - VPC's have default security groups
    - Must be explicitly associated with and EC2 instance
    - By default all outboud traffic is allowed
- Network ACL's
    - Works at the subnet level with an VPC
    - Enables you to allow and deny traffic
    - Each VPC has a default ACL that allows all inbound and outbound traffic
    - Custom ACL's deny all traffic until rules are added
- AWS VPN
    - Createsw an encrypted tunnel into your VPC
    - Can be used to connect your data center or even individual client machines
    - Supported in two services:
        - Site-to-site VPN
        - Client VPN

###    Protecting Infrastructure from Attacks

####    Security Services
- AWS Shield (anti DDoS)
    - Provides protection against DDoS attacks for apps running on AWS
    - Enables on-going threatt detection and mitigation
    - Has two different service levels:
        - Standard
        - Advanced
- Amazon Macie (Data protection service)
    - Utilizes machine learning to analyze data stored in Amazon S3
    - It can detect personal information and intellectual property in S3
    - Provides dashboards that show how the data is being stored and accessed
    - Enables alerts if it detects anything unusual about data access
- Amazon Inspector (Automated security assessment service)
    - Enables scanning of Amazon EC2 instances for security vulnerabilities
    - Charged by instance per assesment run
    - two types of rules packages:
        - Network reachability assessment
        - Host assessment
    
###    Deploying Pre-defined Solutions
- AWS Service Catalog
    - Targeted to serve as an organizational service catalog for the cloud
    - Can include single server image to multi-tier custom applications
    - Enables organizations to leverage services that meet compliance
    - Supports a lifecycle for services released in the catalog
- AWS Marketplace
    - Curated catalog of third-party solutions for customers to run on AWS
    - Provides AMI's, CloudFormation stacks, and SaaS based solutions
    - Enables different pricing options to overcome licensing in the cloud
    - Charges appear on your AWS bill

###    Developer Tools
- AWS CodeCommit (AWS github)
    - Managed source control service
    - Utilizes Git for repositories
    - Control access with IAM policies
    - Serves as an alternative to Github and BitBucket
- AWS CodeBuild (CI)
    - Fully managed build and continuuous integration service on AWS
    - Don't have to worry about maintaining infrastructure
    - Charged per minute for compute resources you utilize
- AWS CodeDeploy
    - Managed deployment service for deploying your custom applications
    - Deploy to Amazon EC2, AWS Fargate, AWS Lambda, and on-premise servers
    - Provides dashboard for deployment in the AWS Console
- AWS CodePipeline (AWS jenkins)
    - Fully-managed continuous delivery service on AWS
    - Provides the capabilities to automate building, testing, and deploying
    - Integrates with other developer tools as well as Github
- AWS CodeStar
    - Workflow tool that automates the use of the other developer services
    - Creates a complete continuous delivery toolchain for a custom application
    - Provides custom dashboards and configurations in the AWS Console
    - You are only charged for the other services you leverage
