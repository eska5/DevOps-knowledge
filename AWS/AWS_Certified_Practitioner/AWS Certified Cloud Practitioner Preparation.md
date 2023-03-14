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

#    Understanding AWS Core Services

###    Interacting with AWS
