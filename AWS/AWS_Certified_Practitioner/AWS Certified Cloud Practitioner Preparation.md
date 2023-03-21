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
