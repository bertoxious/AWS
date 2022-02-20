# AWS

## IAM 
- Identity and Access Management -> A Global Service Because in IAM we are creating users and will assign them to groups.    
- The Root account created should not be used or shared.  
- Users are people within your organisation and can be grouped.  
- Groups only contains users and not other groups.  
- Users don't have to belong to a group and a user can belong to multiple groups.  
- Users or Groups can be assigned JSON documents called Policies. These policies define the permisssions of the users.  
- In AWS we apply the least privilege principle i.e. don't give more permissions than a user needs.  

## How users can access AWS  
- AWS Management Console (protected by password + MFA)  
- AWS CLI (protected by access keys)  
- AWS SDK (for code: protected by access keys)  

## Access Keys  
- These are generated through AWS console.  
- Users can manage their own access keys.  
- Access Key ID similar to username and Secret Access Key similar to password.  

## IAM Security tools  
- IAM Credentials Report(account-level) a report that lists all your account's users and the status of their various credentials.  
- IAM Access Advisor(user-level) shows the service permissions granted to a user and when those services were last accessed. You can use these permissions to revise your policies.  
## AWS BUDGET SETUP  
- From root account allow IAM user to access the billing information.  
- Billing -> Budgets -> Create Budget -> Cost Budget -> Setup ur budget    

## EC2 - Elastic Compute Cloud - Infrastructure as a Service.  
It mainly consists in the capability of:
- Renting Virtual Machines (EC2)
- Storing data on virtual drives (EBS)
- Distributing load across machines (ELB)
- Scaling the services using and Auto Scaling Group (ASG)

### EC2 Sizing and Configuration Options  
- Operating System: Linux, Windows, MacOS  
- How much computer power and cores (CPU)  
- How much RAM  
- How much storage space :  
- - Network attached (EBS and EFS)  
- - Hardware attached (EC2 instance store)  
- Network card: Speed of the card, Public IP address  
- Firewall rules: security group  
- Bootstrap Script (configure at first launch): EC2 User Data

### EC2 user data
- Is it possible to bootstrap our instances using an EC2 User Data script.  
- bootstraping means launching commands when a machine starts.  
- That script is run only once at the instance first start.  
- EC2 user data is used to automate boot tasks such as: Installing updates, Installing software, Downloading common files from internet etc. 
- EC2 user data scripts run with the root user.  i.e any command you write must have the sudo rights.  

### Creating an EC2 Instance  
Services -> EC2 -> Instances -> Launch Instances -> Now choose an AMI(Amazon Machine Image) Choose Free tier AMIs -> Choose Instance Type t2.micro(Free) -> Configure Instance Details network vpc (virtual private cloud) Can also add user data which would run first at the launch of ec2 instance -> Create a new Key Pair 
### Types of EC2 instances https://aws.amazon.com/ec2/instance-types/
### m5.2xlarge
- m : instance class
- 5 : generation (AWS improves over time)
- 2xlarge : size within the instance class 

General Purpose Instances  
- Great for diversity of workloads such as web servers or code repositories  
- Good Balance b/w Compute, Memory and Networking t2.micro is an example of General Purpose EC2 Instance  

Compute Optimized Instances  
- Great for compute-intensive tasks that require high performance processors  
- Batch processing workloads, Media transcoding, high performance web servers, high performance computing, scientific modeling and machine learning and dedicated gaming servers.  
Memory Optimized Instances  
- Fast performance workloads that process large data sets in memory  
- High performance, relational/non-relational databases, Distributed web scale cache stores, In memory databases optimized for Businsess Intelligence, Applications performing real-time processing of big unstructured data.  

Storage Optimized Instances  
- Great for storage intensice tasks that require high, sequential read and write access to large data sets on local storage.  
- High frequency online transaction processing (OLTP) systems, Relational and No SQL Databases, Cache for in memory databases eg redis, Data warehousing applications, Distributed file systems  

__[EC2 instances info](https://instances.vantage.sh/)__

## Security Groups
- Security groups are fundamentals of network security in AWS 
- They control how traffic is allowed into or out of our EC2 instances.  
- Security groups only contain allow rules.  
- Security groups rules can reference by IP or by security group. 
- Act as firewall on ec2 intances.  
- They regulate : Access to ports, Authorised IP ranges IPv4 and IPv6 , Control of inbound network(from other to the instance), Control of outbound network(from intance to the other)

| Type | Protocol | Port Range | Source | Description | 
| --- | --- | --- | --- | --- | 
| type of connection | TCP | the port of the instance | Represent an ip address | Description for your notes | 

- Security Groups can be attached to multiple instances 
- Locked down to a region or VPC combination 
- Does live outside the EC2 if traffic is blocked the EC2 instance won't see it  
- Its good to maintain one separate security group for SSH access 
- If application is not accessible (time out), this is an security group issue. 
- If application gives a connection refused error, then it's application error or it's not launched 
- All inbound traffic is blocked by default 
- All outbound traffic is authorised by default 

Classic ports to know 
22 = SSH (Secure Shell) - log into a Linux instance
21 = FTP (File Transport Protocol) - upload files into a file share 
22 = SFTP (Secure File Transport Protocol) - upload files using SSH 
80 = HTTP - access unsecured websites 
443 = HTTPS - access secured websites
3389 = RDP (Remote Desktop Protocol) - log into a Windows instance 

