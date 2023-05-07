# Module 1

### Three types of Deployment models for cloud computing
1. **Cloud-based Deployment**
	- Run everything on cloud
	- Move existing apps to cloud
	- Create new apps on cloud
2. **On-Premises Deployment**
	- Use virtualization and resource management tools on existing on-premises hardware
	- Typically legacy
3. **Hybrid Deployment**
	- Use cloud-based resources for on-premises hardware
	- Useful for legacy systems that need to be on-prem
		
### Benefits of cloud computing
- Pay as you go instead of huge upfront cost
- Don't have to guess capacity
- Don't have to maintain data centers
- Easier and faster scaling
- Easy global presense
	
### Module 1 Quiz:
- What is cloud computing?
	- On-demand delivery of IT resources and applications through the internet with pay-as-you-go pricing
- What is another name for on-premises deployment?
	- Private cloud deployment
- How does the scale of cloud computing help you to save costs?
	- The aggregated cloud usage from a large number of customers results in lower pay-as-you-go prices.
	
# Module 2:

**Amazon Elastic Compute Cloud (Amazon EC2)**

### EC2 Instance Families
- **General Purpose**
	- Balanced resources
	- Good for webservers
- **Compute Optimized**
	- Good for compute intensive tasks
	- Gaming servers, High Performance Computing (HPC), Scientific modeling, etc.
- **Memory Optimized**
	- For memory intensive tasks
- **Accelerated Computing**
	- Utilize hardware accelerators
	- Good for floating point calculations, graphics processing, data pattern matching, etc.
- **Storage Optimized**
	- High performance for locally stored data
		
### EC2 Pricing
- **On-Demand**
- **Savings Plans**
	- Lower prices if you can commit to a 1 or 3 year term.
	- Savings up to 72%
- **Reserved Instances**
	- Suited for steady state workloads / predictable usage.
	- Savings up to 75%
	- 1 to 3 year term
	- Payment options include all up front, some up front, and no up front.
- **Spot instances**
	- Lets you use spare instances that AWS isn't using.
	- AWS can stop your instance at any time with a 2 minute warning.
	- Savings up to 90%.
- **Dedicated Hosts**
	- You get your own host
	- No Multitenancy

**Multitenancy** - Sharing underlying hardware between virtual machines.
	
**Vertical Scaling** - Giving an EC2 instance more or less CPU and RAM.

### EC2 Scaling

**Amazon EC2 Auto Scaling (Horizontal Scaling)**
- Automatically add or remove Amazon EC2 instances in response to changing application demand.
- Two approches (can use both together!):
	1. **Dynamic**
			- Responds to changing demand.
	2. **Predictive**
			- Schedules the right number of EC2 instances based on predicted demand.
- You can set the number of minimum instances, desired instances, and maximum instances.
		
**Elastic Load Balancing (ELB)** - Automatically distributes incoming application traffic across multiple resources, such as Amazon EC2 instances. 

### Messaging and queuing
- **Amazon Simple Queue Service (Amazon SQS)**
	- Send, store, and receive messages between software components.
- **Amazon Simple Notification Service (Amazon SNS)**
	- Can also send, store, and receive messages.
	- Publish/Subscribe model.
	- Create topics that will send notifications to the subscribers.
	- Subscribers can be end points like AWS Lambda functions, HTTP hooks, etc.
	- Can send notifications to end users via push, SMS, email, etc.
	
### Serverless

**Serverless** - Cannot see or access the underlying infrastructure.
	
- **AWS Lambda**
	- A service that lets you run code without needing to provision or manage servers.
	- Charges apply only when your code is running.
	
- **Containers** - Containers provide you with a standard way to package your 
		application's code and dependencies into a single object.
		
	- **Amazon Elastic Container Service (Amazon ECS)**
		- A highly scalable, high-performance container management system that enables 
			you to run and scale containerized applications on AWS.
		- Uses Docker
	- **Amazon Elastic Kubernetes Service (Amazon EKS)**
		- A fully managed service that you can use to run Kubernetes on AWS.
		- Kubernetes is open-source software that enables you to deploy
			and manage containerized applications at scale.
	- **AWS Fargate**
		- A serverless compute engine for containers. It works with both Amazon ECS and Amazon EKS.
		- Don't need to provision or manage servers.
			
### Module 2 Quiz
- You want to use an Amazon EC2 instance for a batch processing workload. What would be the best Amazon EC2 instance type to use?
	- Compute optimized
- What are the contract length options for Amazon EC2 Reserved Instances?
	- 1 year or 3 years
- You have a workload that will run for a total of 6 months and can withstand interruptions. What would be the most cost-efficient Amazon EC2 purchasing option?
	- Spot Instance
- Which process is an example of Elastic Load Balancing?
	- Ensuring that no single Amazon EC2 instance has to carry the full workload on its own.
- You want to deploy and manage containerized applications. Which service should you use?
	- Amazon Elastic Kubernetes Service (Amazon EKS)

# Module 3:
- Reasons for selecting a region
	- Compliance with data governance and legal requirements.
	- Proximity to customers
	- Available features
	- Pricing	
		
Each region is comprised of multiple availability zones
	
**Availability Zone** - One or a group of data centers
		
- **Amazon Cloudfront**
	- Amazon's CDN
	- Uses edge locations to accelerate communication and content delivery with users
	
- **Edge locations**
	- A site that Amazon CloudFront uses to store cached copies of your content
		closer to your customers for faster delivery.
		
- **AWS Route 53 (DNS)**
	- Amazon's Domain Name System

- **AWS Outposts**
	- Pretty much a mini region thats inside your own building.
	
- Ways to interact with AWS services:
	- **AWS Management console (website)**
	- **AWS Command Line Interface (CLI)**
	- **Software Development Kits (SDKs)**
	
- **AWS Elastic Beanstalk**
	- You provide code and configuration settings, and Elastic Beanstalk deploys theresources necessary to perform the following tasks
		- Adjust Capacity
		- Load balancing
		- Automatic scaling
		- Application health monitoring

- **AWS CloudFormation**
	- You can build an environment by writing lines of code instead of using the AWS Management Console to individually provision resources.
			
### Module 3 Quiz
- Which statement is TRUE for the AWS global infrastructure?
	- A Region consists of two or more Availability Zones.
- Which factors should be considered when selecting a Region?
	- Compliance with data governance and legal requirements
	- Proximity to your customers
- Which statement best describes Amazon CloudFront?
	- A global content delivery service
- Which site does Amazon CloudFront use to cache copies of content for
	faster delivery to users at any location?
	- Edge location
- Which action can you perform with AWS Outposts?
	- Extend AWS infrastructure and services to your on-premises data center.

# Module 4