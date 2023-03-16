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

