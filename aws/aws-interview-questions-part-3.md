#AWS Interview Questions

Q1: List the components required to build Amazon VPC?
Ans: Subnet, Internet Gateway, NAT Gateway, HW VPN Connection, Virtual Private Gateway, Customer Gateway, Router, Peering Connection, VPC Endpoint for S3, Egress-only Internet Gateway.

Q2: How do you safeguard your EC2 instances running in a VPC?
Ans: Security Groups can be used to protect your EC2 instances in a VPC. We can configure both INBOUND and OUTBOUND traffic in a Security Group which enables secured access to your EC2 instances. Security Group automatically denies any unauthorized access to your EC2 instances.

Q3: In a VPC how many EC2 instances can you use?
Ans: Initially you are limited to launch 20 EC2 Instances at one time. Maximum VPC  size is 65,536 instances.

Q4: Can you establish a peering connection to a VPC in a different REGION?
Ans: Not possible. Peering Connection are available only between VPC in the same region.

Q5: Can you connect your VPC with a VPC owned by another AWS account?
Ans: Yes, Possible. Provided the owner of other VPCs accepts your connection.

Q6: What are all the different connectivity options available for your VPC?
Ans: Internet Gateway, Virtual Private Gateway, NAT, EndPoints, Peering Connections.

Q7: Can a EC2 instance inside your VPC connect with the EC2 instance belonging to other VPCs?
Ans: Yes, Possible. Provided an Internet Gateway is configured in such a way that traffic bounded for EC2 instances running in other VPCs.

Q8: How can you monitor network traffic in your VPC?
Ans: It is possible using Amazon VPC Flow-Logs feature.

Q9: Difference between Security Groups and ACLs in a VPC?
Ans: A Security Group defines which traffic is allowed TO or FROM  EC2 instance. Whereas ACL, controls at the SUBNET level, scrutinize the traffic TO or FROM a Subnet.

Q10: Hon an EC2 instance in a VPC establish the connection with the internet?
Ans: Using either a Public IP or an Elastic IP.

Q11: Different types of Cloud Computing as per services?
Ans:  PAAS (Platform As A Service), IAAS (Infrastructure As A Service), SAAS (Software As A Service)

Q12: What is Auto Scaling?
Ans: Creating duplicate instances during heavy business hours. Scale-IN and Scale-OUT are two different statues of Scaling. Scale-IN: Reducing the instances. Scale-OUT: Increasing the instances by duplicating.

Q13: What is AMI?
Ans: AMI is defined as Amazon Machine Image. Basically it’s a template comprising software configuration part. For example, Operating System, DB Server, Application Server, etc.,

Q14: Difference between Stopping and Terminating the Instances?
Ans: When you STOP an instance it is a normal shutdown. The corresponding EBS volume attached to that instance remains attached and you can restart the instance later. When you TERMINATE an instance it gets deleted and you cannot restart that instance again later. And any EBS volume attached with that instance also deleted.

Q15: When you launch a standby Relational Database Service instance will it be available in the same Available Zone?
Ans: Not advisable. Because the purpose of having standby RDS  instance is to avoid an infrastructure failure. So you have to keep your standby RDS service in a different Availability Zone, which may have different infrastructure.

Q16: Difference between Amazon RDS, DynamoDB and Redshift?
Ans: RDS is meant for structured data only. DynamoDB is meant for unstructured data which is a NoSQL service. Redshift is a data warehouse product used for data analysis.

Q17: What are Lifecycle Hooks?
Ans: Lifecycle Hooks are used in Auto Scaling. Lifecycle hooks enable you to perform custom actions by pausing instances as an Auto Scaling group launches or terminates them. Each Auto Scaling group can have multiple lifecycle hooks.

Q18: What is S3?
Ans: S3 stands for Simple Storage Service, with a  simple web service interface to store and retrieve any amount of data from anywhere on the web.

Q19: What is AWS Lambada?
Ans: Lambda is an event-driven platform. It is a compute service that runs code in response to events and automatically manages the compute resources required by that code.

Q20: In S3 how many buckets can be created?
Ans: By default 100 buckets can be created in a region.

Q21: What is CloudFront?
Ans: Amazon CloudFront is a service that speeds up transfer of your static and dynamic web content such as HTML files, IMAGE files., etc., CloudFront delivers your particulars thru worldwide data centers named Edge Locations.

Q22: Brief about S3 service in AWS?
Ans: S3, a Simple Storage Service from Amazon. You can move your files TO and FROM S3. Its like a FTP storage. You can keep your SNAPSHOTS in S3. You can also ENCRYPT your sensitive data in S3.

Q23: Explain Regions and Available Zones in EC2?
Ans: Amazon has hosted EC2 in various locations around the world. These locations are called REGIONS. For example in Asia, Mumbai is one region and Singapore is another region. Each region is composed of isolated locations which are known as AVAILABLE ZONES.    Region is independent. But the Available Zones are linked thru low-latency links.

Q24: What are the two types of Load Balancer?
Ans: Classic LB and Application LB. ALB is the Content Based Routing.

Q25: Can a AMI be shared?
Ans: Yes. A developer can create an AMI and share it with other developers for their use. A shared AMI is packed with the components you need and you  can customize the same as per your needs. As you are not an owner of a shared AMI there is a risk always involved.

Q26: What is a Hypervisor?
Ans: A Hypervisor is a kind of software that enables Virtualization. It combines physical hardware resources into a platform which is delivered virtually to one or more users. XEN is the Hypervisor for EC2.

Q27: Key Pair and its uses?
Ans: You use Key Pair to login to your Instance in a secured way. You can create a key pair using EC2 console. When your instances are spread across regions you need to create key pair in each region.

Q28: What is the feature of ClassicLink?
Ans: ClassicLink allows instances in EC2 classic platform to communicate with instances in VPC using Private IP address. EC2 classic platform instances cannot not be linked to more than one VPC at a time.

Q29: Can you edit a Route Table in VPC?
Ans: Yes. You can always modify route rules to specify which subnets are routed to the Internet gateway, the virtual private gateway, or other instances.

Q30: How many Elastic IPs can you create?
Ans: 5 VPC Elastic IP addresses per AWS account per region

Q31: Can you ping the router or default gateway that connects your subnets?
Ans: NO, you cannot. It is not supported. However you can ping EC2 instances within a VPC, provided your firewall, Security Groups and network ACLs allows such traffic.

Q32: How will you monitor the network traffic in a VPC?
Ans: Using Amazon VPC Flow Logs feature.

Q33: Can you make a VPC available in multiple Available Zones?
Ans: Yes.

Q34: How do you ensure an EC2 instance is launched in a particular Available Zone?
Ans: After selecting your AMI Template and Instance Type, in the third step while configuring the instance you must select the SUBNET in which you wish to launch your instance. It will be launched in the AZ associated with that SUBNET.

Q35: For Internet Gateways do you find any Bandwidth constraints?
Ans: NO. Normally an IG is HORIZONTALLY SCALLED, Redundant and Highly Available. It is not having nay Bandwidth constraints usually.

Q36: What is the significance of a Default VPC?
Ans: When you launch your instances in a Default VPC in a Region, you would be getting the benefit of advanced Network Functionalities. You can also make use of Security Groups, multiple IP addresses, and multiple Network interfaces.

Q37: Can you make use of default EBS Snapshots?
Ans: You can use, provided if it is located in the same region where your VPC is presented.

Q38: What will happen when you delete a PEERING CONNECTION in your side?
Ans: The PEERING CONNECTION available in the other side would also get terminated. There will no more traffic flow.

Q39: Can you establish a Peering connection to a VPC in a different region?
Ans: NO. Its possible between VPCs in the same region.

Q40: Can you connect your VPC with a VPC created by another AWS account?
Ans: Yes. Only when that owner accepts your peering connection request.

Q41: When you delete your DB instance what will happen to your backups and DB snapshots?
Ans: When a DB instance is deleted, RDS retains the user-created DB snapshot along with all other manually created DB snapshots. Also automated backups are deleted and only manually
 created DB Snapshots are retained.

Q42: What is the significance of an Elastic IP?
Ans: The Public IP is associated with the instance until it is stopped or terminated Only. A Public IP is not static. Every time your instance is stopped or terminated the associated Public IP gets vanished and a new Public IP gets assigned with that instance. To over come this issue a public IP can be replaced by an Elastic IP address, which stays with the instance as long as the user doesn’t manually detach it. Similarly when if you are hosting multiple websites on your EC2 server, in that case you may require more than one Elastic IP address.

Q43: How will you use S3 with your EC2 instances?
Ans: Websites hosted on your EC2 instances can load their static contents directly from S3. It provides highly scalable, reliable, fast, inexpensive data storage infrastructure.

Q44: Is this possible to connect your company datacenter to Amazon Cloud?
Ans: Yes, you can very well do this  by establishing a VPN connection between your company’s network and Amazon VPC.

Q45: Can you change the Private IP of an EC2 instance while it is running or stopped?
Ans: A Private IP is STATIC. And it is attached with an instance throughout is lifetime and cannot be changed.

Q46: What is the use of Subnets?
Ans: When a network has more number of HOSTS, managing these hosts can be tedious under a single large network. Therefore we divide this large network into easily manageable sub-networks (subnets) so that managing hosts under each subnet becomes easier.

Q47: What is the use of Route Table?
Ans: Route Table is used to route the network pockets. Generally one route table would be available in each subnet. Route table can have any no. of records or information, hence attaching multiple subnets to a route table is also possible.

Q48: Can you use the Standby DB instance for read and write along with your Primary DB instance?
Ans: Standby server cannot be used in parallel with primary server unless your Primary instance goes down.

Q49: What is the use of Connection Draining?
Ans: Connection Draining is a service under Elastic Load Balancing. It keeps monitoring the healthiness of the instances. If any instance fails Connection Draining pulls all the traffic from that particular failed instance and re-route the traffic to other healthy instances.

Q50: What is the role of AWS CloudTrail?
Ans: CloudTrail is designed for logging and tracking API calls. Also used to audit all S3 bucket accesses.

Q51: What is the use of Amazon Transfer Acceleration Service?
Ans: ATA service speeds up your data transfer with the use of optimized network paths. Also, speed up your CDN up to 300% compared to normal data transfer speed

Q52: What is the name of AWS CEO or Chief ?
Jeff Bezos
Lisa Su
Denise Morrison
Ans: Jeff Bezos

Q53: EC2 officially launch in …..
2002
2006
2008
Ans: 2006

Q54: S3 Launched officially lunched in …..
2002
2006
2008
Ans: 2006

Q55: You cannot store unlimited data in Amazon Web Services…..
True
False
Ans: False

Q56: Rapid provisioning allows you to very quickly spin up a new virtual machine with minimal effort. True or false ?
True
False
Ans: True

Q57: A hybrid setup is one in which part of your resources are AWS and the rest are with another cloud provider. True or False ?
True
False
Ans: False

Q58: As an added layer of security for AWS management, which of the following should be you do ?
Create multiple Admin accounts
Generate a new security key each time you log in
Create IAM users
Ans: Create IAM users
EC2, Elastic Computing & Instances Types

Q59: Is AMI template ?
True
False
Ans: True

Q60: EC2 Instances are Virtual Server in AWS
True
False
Ans: True

Q61: What does “elastic” refer to in Elastic Compute Cloud(EC2)? Select all that apply.
Increasing and decreasing capacity as needed
Monitoring services on multiple devices
Operating on Mac, Windows and Linux
Paying only for running virtual machines
Stretching applications across virtual machines
Ans: 1. Increasing and decreasing capacity as needed & 4. Paying only for running virtual machines

Q62: You can upload a custom configuration virtual image and sell it on the AWS Marketplace. True or false ?
True
False
Ans: True

Q63: EC2 Machine types define which of the following ?
AWS Region
Core Count
User Location
Ans: Core Count

Q64: Which is default instance type
On-demand
RI
Spot instance
Ans: On-demand

Q65: What is Elastic Computing ?
Data will be replicate to different AZs
You can spin up and spin down VMs
Automatically VMs will be add and remove
Ans: You can spin up and spin down VMs

Q66: You can upload a custom configuration virtual image and sell it on the AWS Marketplace. True or false ?

True
False
Ans: True

Q67: EC2 Machine types define which of the following ?
AWS Region
Core Count
User Location
Ans: Core Count

Q68: Which is default instance type
On-demand
RI
Spot instance
Ans: On-demand

Q69: What is Elastic Computing ?
Data will be replicate to different AZs
You can spin up and spin down VMs
Automatically VMs will be add and remove
Ans: You can spin up and spin down VMs

Q70: Can We launch multiple instances with same AMI ?
True
False
Ans: True

Q71: PEM file is one time physical password…
True
False
Ans: True

Q72: Windows user required PPK file to connect Linux instance hosted on AWS.
True
False
Ans: True

Q73: You can purchase time on EC2 directly from other users and specify the price you want to pay. True or false ?
True
False
Ans: True

Q74: Which of the following might prevent your EC2 instance from appearing in the list of instances?
EC2 is not selected
Correct region is not selected
AWS marketplace is not selected
Ans: Correct region is not selected

Q75: Which of the following main reason to terminate an unused EC2 instance ?
Security Concerns
Additional fees
Data Loss
Ans: Additional fees

Q76: Which AWS service exists only to redundantly cache data and images ?
AWS Availability Zones
AWS Edge Locations
AWS Regions
Ans: AWS Edge Locations

Q77: Regions, AZs and Edge Locations all terms are same…
True
False
Ans: False

Q78: AWS every service is available at every regions….
True
False
Ans: False

Q79: Premium support is Available in AWS for Developer, Business & Enterprise level ?
True
False
Ans: True

Q80: Can you add new Debit/Credit card in your AWS Account ?
True
False
Ans: True

Q81: Can you increase micro to large of instance ?
True
False
Ans: True

Q82: On-demand instances is based on a bid mechanism.
True
False
Ans: False

Q83: RI can be sold on the AWS marketplace?
True
False
Ans: True

Q84: Which is default types options in AWS?
On-demand
RI
Spot instance
Ans: On-demand

Q85: What are On-demand, RI and Spot instances ? Which instance is best on Production?
On-demand
RI
Depends on Application or Website
Ans:  Depends on Application or Website

Q86: Which is most expensive options in instance ?
On-demand
RI
Spot instance
Ans: On-demand

Q87: Amazon S3 is internet accessible storage via HTTP /HTTPS
True
False
Ans: True

Q88: Amazon S3 is not a object level of storage
True
False
Ans: False

Q89: Amazon S3 is storage for the Internet
True
False
Ans: True

Q90: Temporary storage access speed is not guaranteed.
True
False
Ans: True

Q91: There is 99.99% SLA(Service Level Agreement) for temporary storage.
True
False
Ans: False

Q92: Ephemeral storage is block-level storage ?
True
False
Ans: True

Q93: Single object size is up to 5 TB in Amazon S3.
True
False
Ans: True

Q94: You can create unlimited bucket size in Amazon S3.
True
False
Ans: True

Q95: By default, Instance-Backed and EBS-Backed root volumes delete all data. However, when using EBS-Backed storage, you can configure it to save the data on the root volume. True or false ?
True
False
Ans: True

Q96: You can switch from an Instance-Backed to an EBS-Backed root volume at any time. True or False ?
True
False
Ans: False

Q97: When using an EBS-Backed machine, you can override the terminate option and save the root volume. True or False ?
True
False
Ans: True

Q98: Which of the following is a service of AWS Simple Storage Service(S3)? Select all that apply.
Database Indexing
File searching
Secure Hosting
Storage Scaling
Ans: 3. Secure Hosting & 4. Storage Scaling

Q99: What’s the difference between instance store and EBS?
Issue
I’m not sure whether to store the data associated with my Amazon EC2 instance in instance store or  in an attached Amazon Elastic Block Store (Amazon EBS) volume. Which option is best for me?
Resolution
Some Amazon EC2 instance types come with a form of directly attached, block-device storage known as the instance store. The instance store is ideal for temporary storage, because the data stored in instance store volumes is not persistent through instance stops, terminations, or hardware failures. You can find more detailed information about the instance store at Amazon EC2 Instance Store.
For data you want to retain longer-term, or if you need to encrypt the data, we recommend using EBS volumes instead. EBS volumes preserve their data through instance stops and terminations, can be easily backed up with EBS snapshots, can be removed from instances and reattached to another, and support full-volume encryption. For more detailed information about EBS volumes, see Features of Amazon EBS.

Q100: BS can be attached to any running instance that is in the same Availability Zone ?
True
False
Ans: True

Q101: EBS is internet accessible
True
False
Ans: False

Q102: EBS has persistent file system for EC2
True
False
Ans: True

Q103: EBS supports incremental snapshots
True
False
Ans: True

Q104: Amazon Glacier enables customers to offload the administrative burdens of operating and scaling storage to AWS.
True
False
Ans: True

Q105: Amazon Glacier is a great storage choice when low storage cost is paramount.
True
False
Ans: True

Q106: Data is rarely retrieved, and retrieval latency of several hours is acceptable in Glacier
True
False
Ans: True

Q107: Glacier is basically for data archival
True
False
Ans: True

Q108: It is very cheap storage
True
False
Ans: True

Q109: Glacier has very, very slow retrieval times
True
False
Ans: True

Q110: By Default, Instance-Backed and EBS-Backed root volumes delete all data. However, when using EBS-Backed storage, you can configure it to save the data on the root volume.
True
False
Ans: True

Q111: You can switch from an Instance-Backed to an EBS-Backed root volume at any time.
True
False
Ans: False

Q112: When using an EBS-Backed machine, you can override the terminate option and save the root volume.
True
False
Ans: True

Q113: VPC is Private, Isolated, Virtual Network
True
False
Ans: True

Q114: VPC would be logically isolated network in AWS cloud
True
False
Ans: True

Q115: VPC is also give control of network architecture
True
False
Ans: True

Q116: VPC is also going to enhanced security
True
False
Ans: True

Q117: VPC has ability to interwork with other organizations
True
False
Ans: True

Q118: VPC does not enable hybrid cloud(site-to-site VPN)
True
False
Ans: False

Q119: Route Table is a set of Rules tells the direction of network
True
False
Ans: True

Q120: Security Group is a subnet level of security
True
False
Ans: False

Q121: NACLs(Network Access Lists) is a resource level of security
True
False
Ans: False

Q122: Any default stack is available in Cloud Formation ?
Ans:  You can not create default stack but you can choose the type of stack to create e.g :
A sample stack
A Linux-based chef 12 stack
A Windows-based Chef 12.2 stack
A Linux-based Chef 11.10 stack
Q123: What is the difference between Stack and Template in Cloud Formation ?
Ans: Stack : Cloud-based applications usually require a group of related resources—application servers, database servers, and so on—that must be created and managed collectively. This collection of instances is called a stack
Q124: We can create multiple server for same stack ?
Ans: you can select one “instance type” e.g: t2.micro at a time but you can set more then one “Webserver Capacity” which is “The initial number of Webserver instances“ means automatically same kind of instances will launch.
Q125: Can you explain the term SQS is pull based, not pushed base.
Ans: It means that you have to actively poll the queue in order to receive a messages.
The messages are pushed into the queue by the producers but pulled out of the queue by the consumers.You have to call the Receive Message action from the consumer in order to get the messages, they are not pushed to you automatically when they arrive.
Q126. How many Elastic IP address can be associated with a single account?
4
10
5
None the above
Ans: 5
Q127. What is the name to the additional network interfaces that can be created and attached to any Amazon EC2 instance in your VPC?
Elastic IP
Elastic Network Interface
AWS Elastic Interface
AWS Network ACL
Ans: Elastic Network Interface
Q128. You have configured ELB with three instances connected to that. If your instances are unhealthy or terminated, the traffic should be automatically replaced to another instance, what type of service can be used to achieve this requirement?
Sticky session
Fault Tolerance
Connection drainage
Monitoring
Ans: Fault Tolerance
Q129. After configuring ELB, you need to ensure that the user requests are always attached to a single instance. What setting can you use?
Session cookie
Cross one load balancing
Connection drainage
Sticky session
Ans: Sticky session
Q130. Which of the following metrics cannot have a cloud watch alarm?
EC2 instance status check failed
EC2 CPU utilization
RRS lost object
Auto scaling group CPU utilization
Ans: RRS lost object
Q131. Which of the below mentioned service is provided by Cloud watch?
Monitor estimated AWS usage
Monitor EC2 log files
Monitor S3 storage
Monitor AWS calls using Cloud trail
Ans: Monitor estimated AWS usage
Q132. A user has Launched an EC2 instance which of the below mentioned statements is not true respect to instance addressing?
The private IP addresses are not reachable from the internet
The user can communicate using the private IP across regions
The private IP address and pubic IP address for an instance are directly mapped to each other using NAT
The private IP address for the instance is assigned using DHCP
Ans: The user can communicate using the private IP across regions
Q133. Which of the following service provides the edge – storage or content delivery system that caches data at different locations?
Amazon RDS
Simple DB
Amazon Cloud Front
Amazon associates web services
Ans: Amazon Cloud Front
Q134. A user is launching an instance under the free usage tier from the AMI with a snapshot size of 50 GB. How can the user launch the instance under the free usage tier?
Launch a micro instance
Launch a micro instance, but in the EBS configuration modify the size of EBS to 50 GB.
Launch a micro instance, but do not store the data of more than 30 GB on the EBS storage.
It is not possible to have this instance under the free usage tier
Ans: It is not possible to have this instance under the free usage tier
Q135. What are the possible connection issues you can face while connecting to your instance?
Connection timed out
Server refused our key
No supported authentication methods available
All of the above
Ans: All of the above
Q136. You are enabled sticky session with ELB. What does it do with your instance?
Routes all the requests to a single DNS
Binds the user session with a specific instance
Binds the user IP with a specific session
Provides a single ELB DNS for each IP address
Ans: Binds the user session with a specific instance
Q137. Which is a main email platform that provides an easy, cost effective way for you to send compliance and receive a response using your own email address and domains?
SES
SNS
SQS
SAS
Ans: SES
Q138. Which type of load balancer makes routing decisions at either the transport layer or the application layer and supports either EC2 or VPC.
Application Load Balancer
Classic Load Balancer
Primary Load Balancer
Secondary Load Balancer
Ans: Classic Load Balancer
Q139. AWS Cloud Front has been configured to handle the customer requests to the web server launched in Linux machine. How many requests per second can Amazon Cloud Front handle?
1000
100
10000
There is no such limit
Ans: There is no such limit
Q140. You are going to launched one instance with security group. While configuring security group, what are the things you have to select?
Protocol and type
Port
Source
All of the above
Ans: Source
Q141. Which is virtual network interface that you can attach to an instance in a VPC?
Elastic IP
AWS Elastic Interface
Elastic Network Interface
AWS Network ACL
Ans: Elastic Network Interface
Q142. You have launched a Linux instance in AWS EC2. While configuring security group, you have selected SSH, HTTP, HTTPS protocol. Why do we need to select SSH?
To verity that there is a rule that allows traffic from your computer to port 22
To verify that there is a rule that allows traffic from EC2 Instance to your computer
Allows web traffic from instance to your computer
Allows web traffic from your computer to EC2 instance
Ans: To verify that there is a rule that allows traffic from EC2 Instance to your computer
Q143. You need to quickly set up an email service because a client needs to start using it in the next hour. Amazon service seems to be the logical choice but there are several options available to set it up. Which of the following options to set up AWS service would best meet the needs of the client?
Amazon SES console
AWS Cloud Formation
SMTP interface
AWS Elastic Beanstalk
Ans: Amazon SES console
Q144.You have chosen a windows instance with Classic and you want to make some change to the security group. How will these changes be effective?
Security group rules cannot be changed
Changes are automatically applied to windows instances
Changes will be effective after rebooting the instance in that security group
Changes will be effective after 24-hours
Ans: Changes are automatically applied to windows instances
Q145. Load Balancer and DNS service comes under which type of cloud service?
IAAS-Network
IAAS-Computational
IAAS-Storage
None of the above
Ans: IAAS-Storage
Q146. You have an EC2 instance that has an unencrypted volume. You want to create another encrypted volume from this unencrypted volume. Which of the following steps can achieve this?
Just simply create a copy of the unencrypted volume, you will have the option to encrypt the volume.
Create a snapshot of the unencrypted volume and then while creating a volume from the snapshot you can encrypt it
Create a snapshot of the unencrypted volume (applying encryption parameters), copy the snapshot and create a volume from the copied snapshot
This is not possible, once a volume is unencrypted, there is no way to create an encrypted volume from this
Ans: Create a snapshot of the unencrypted volume (applying encryption parameters), copy the snapshot and create a volume from the copied snapshot
Q147. Where does the user specify the maximum number of instances with the auto scaling commands?
Auto scaling Launch Config
Auto scaling group
Auto scaling policy
Auto scaling size
Ans: Auto scaling Launch Config
Q148. A user is identify that a huge data download is occurring on his instance he has already set the auto scaling policy to increase the instance count when the network Input Output increase beyond a threshold limits how can the user ensure that this temporary event does not result in scaling
The network I/O are not affecting during data download
The policy cannot be set on the network I/O
There is no way the can stop scaling as it already configured
Suspend scaling
Ans: Suspend scaling
Q149. Which are the types of AMI provided by AWS?
EBS Backed
Instance Store backed
None its volume type and not AMI types
Both A and B
Ans: Both A and B
AWS Interview Questions and Answers for Freshers
Q150. What is the significance of forming Subnets?
A. Because, not enough hosts
B. To manage small number of hosts
C. To utilize the Volume available across different subnets
D. Smartly utilize network that have large number of hosts
The answer is: D
Q2: If you want to launch your instance on a single-tenancy platform, which option you would select against Instance Tenancy Attribute parameter?
A. One to one
B. Sole Owner
C. Dedicated
D. Reserved
The answer is: C
Q151. Which AWS Service you would use to transfer objects from your data center, when you are using Amazon CloudFront?
A. AWS CloudWatch
B. AWS SNS Service
C. AWS SMS Service
D. AWS Direct Connect
The answer is: D
Q152 _____________ is a fully managed Data Warehouse service from AWS?
A. Amazon Redshift
B. Amazon Neptune
C. Amazon Aurora
D. Amazon DynamoDB
The answer is: A
Q153. Which of the following statements are applicable to AWS Elastic File System(EFS)?
A. EFS provides simple, scalable file storage for use with Amazon EC2
B. EFS with MS-Windows based EC2 instances is not supported
C. EFS supports the Network File System version 4 protocol
D. All of the above
The answer is: D
Q154. What is the role of Connection Draining?
A. Helps to launch an EC2 instance
B. Automatically terminates instances which are not in use
C. Establishes connection between EC2 and RDS instances
D. Auto Scaling wait for outstanding requests to complete before terminating instances when CD is enabled
The answer is: D
Q155. What is the use of Lambda?
A. Lambda is used for running server-less applications
B. It is a testing tool from AWS
C. It is a database service from AWS
D. It is an Anti Virus software from AWS
The answer is: A
Q156. What is Application Load Balancing?
A. It is a feature of Elastic Load Balancing
B. Use to distribute traffic to different Target Groups
C. It is a service generating Elastic IPs for AWS customers
D. It is a kind of Firewall
The answers are: A and B
Q157. What are the uses of Elastic Beanstalk?
A. Quickly deploy and manage applications in the AWS Cloud
B. Supports Java, .NET, Node.js, PHP, Python applications
C. It is an Application Server from AWS
D. Use to deploy only Java-Beans applications
The answers are: A and B
Q158. Can you connect your company’s datacenter to the Amazon Cloud network?
A. Not possible
B. You can connect thru a Dedicated N/W line
C. By establishing a Virtual Private Network (VPN) between your datacenter and VPC
D. Connect with a hotline
The answer is: C
Q159. You have commissioned PRIVATE servers in your premises. You also distributed some of your workloads with the PUBLIC cloud. What type of architecture is this?
A. Virtual Private Cloud
B. Community Cloud
C. Public Cloud
D. Hybrid Cloud
The answer is: D
Q160. DynamoDB _______________________. Which one of the following is true regarding DynamoDB?
A. Manages Notification Service
B. Stores Metadata
C. Manages Queue Service
D. None of the above
The answer is: B
Q161: What are the significances of AWS CloudTrail?
A. Takes care of Message Queuing Service
B. It enables governance, compliance, operational auditing and risk auditing of your AWS account.
C. Used as a database service
D. It provides an event history of your AWS account activities
The answers are: B and D
Q162. Which one is a global Content Delivery Network service that securely delivers data, videos, applications, and APIs to your viewers with low latency and high transfer speeds?
A. Amazon CloudWatch
B. Amazon CloudFront
C. Amazon CloudTrail
D. Amazon VPC
The answer is: B
Q163. Is AWS offering Reserved Instances facility for Multiple-Subnet deployments?
A. Yes, available for all kind of instances
B. No, available only for Dedicated Tenancy
C. Offering only for LINUX based instances
D. None of the above
The answer is: A
Q164. Select the correct statement from the below:
A. You can have multiple ACLs for a subnet
B. Security Group is not necessary for an EC2 instance
C. You can attach multiple Zones/Subnets to a Route Table
D. You can create S3 bucket using AWS AMI templates
The answer is: C
Q165. Name the AWS DB Service which is Server-Less and NoSQL DB which delivers consistent single-digit millisecond latency at any scale?
A. Amazon Redshift
B. Amazon Neptune
C. Amazon Aurora
D. Amazon DynamoDB
The answer is: D
Q166. Is this advisable to keep your Standby-Database instance in the same zone where your primary instance is running?
A. Yes, you can keep
B. Possible only for MySQL instance
C. No, not recommended for any kind of DB instance
D. Recommended only for MS-SQL instance
The answer is: C
Q167. Can objects in S3 be delivered by Amazon CloudFront?
A. Yes, you can place any objects in S3 which CloudFront quickly delivers
B. CloudFront delivers only movie type objects
C. No, S3 cannot be integrated with CloudFront
D. Amazon VPC will deliver the objects
The answer is: A
Q168. What you should do if you want to launch an EC2 instance with a pre-allocated private IP address?
A. Launch it in a Subnet Group
B. Launch the instance from a Private AMI
C. Assign EIP address to that instance
D. Launch that instance in AWS VPC cloud
The answer is: D
Q169. Can you edit a Security Group (SG) rules when it is used by multiple EC2 instances? Will new rules apply to all previously running EC2 instances?
A. No, you cannot edit a SG when used by a EC2 instance
B. Yes, you can edit. Immediately apply to all instances.
C. You can edit only the Outbound rules
D. Only Outbound rules apply to all EC2 instances
The answer is: B
Q170. Which of the following statements are true with Route 53?
A. Amazon Route 53 is a scalable and highly available Domain Name System (DNS)
B. Amazon Route 53 is fully compliant with IPv6 as well
C. Will automatically configure DNS settings for your domains
D. Route 53 provides low latency database service
The answers are: A,B and C
Q171. What is a Virtual Private Cloud (VPC)?
A. VPC enables you to launch AWS resources into a virtual network
B. VPC is a virtual network dedicated to your AWS account
C. VPC is used to create domain name for your organization
D. VPC can also be connected to your own office data center
The answers are: A,B and D
Q172. What is an Elastic IP?
A. There is no such IP. Only public & private IPs are valid.
B. Used in Elastic Load Balancing
C. An Elastic IP address is a static IPv4 address
D. An Elastic IP address is for use in a specific region only
The answers are: C and D
Q173. _____________ is a fully managed in-memory data store service offered by Amazon Web Services (AWS)?
A. Amazon Neptune
B. Amazon Redshift
C. Amazon ElastiCache
D. Amazon Aurora
The answer is: C
Q174. In AWS which service is used to create Domain Name for their customers?
A. Amazon CloudWatch
B. Amazon Route53
C. Amazon CloudDomain
D. Amazon VPC
The answer is: B
Q175. Which one is a valid statement regarding EBS-Volumes?
A. You can attach maximum of 5 volumes to an instance
B. You can attach multiple instances to one volume
C. You can attach multiple volumes to a single EC2 instance
D. You cannot attach a additional volume to an instance
The answer is: C
Q176. Which one is a valid statement regarding EBS-Snapshots?
A. You can access Snapshots thru S3 APIs
B. You can store your Snapshots in a S3 BUCKET
C. Snapshots are available only thru EC2 instances
D. You can access your Snapshots thru VPC APIs
The answer is: C
Q178. Which one is the valid scenario?
A. Creating PEERING connection to a VPC in a Different Region
B. Creating PEERING connection between VPCs in Same Region
C. Attaching VOLUME in one subnet/zone with EC2 instance in another subnet/zone
D. Keeping your primary db and secondary db in the same zone
The answer is: B
Q179. How do you connect a VPC to your Office Datacenter?
A. By keeping AWS VPC and Office Datacenter in same IP range
B. Establishing VPN connection between VPC and Datacenter
C. Establishing a dedicated hotlink between VPC and Datacenter
D. You cannot connect VPC and your Datacenter
The answer is: B
Q180. Choose the valid scenarios regarding VPC?
A. You can delete the Default VPC available in your region
B. VPC can span across multiple Availability Zones
C. Trying to launch an instance without having VPC in a region
D. Launching an instance onto a VPC created by you
The answers are: A,B and D
Q181. How the EC2 instances inside a VPC directly access the internet?
A. With the help of instance’s Public IP
B. By attaching a Elastic IP to that instance
C. Internet Gateway enables the access to the internet
D. With the help of Route Table
The answer is: C
Q182. Which one is the highly secured design?
A. Keeping both EC2 and Database instances in a public subnet
B. Keep EC2 in public subnet and Database in private subnet
C. Keep EC2 in public subnet and Database in a S3 bucket
D. Defining ANYWHERE in the DB security group INBOUND rule
The answer is: B
Q183. Keeping your instance in a public subnet and database in a private subnet. What type of cloud deployment model is this?
A. Community Cloud
B. Private Cloud
C. Public Cloud
D. Hybrid Cloud
The answer is: D
Q184. Which service distribute the contents from Edge Locations to the end users to reduce the latency?
A. Amazon CloudWatch
B. Amazon CloudTrail
C. Amazon CloudFront
D. Amazon PushData
The answer is: C
Q185. I am a cloud web service used for hosting your application. Who am I?
A. AWS Route 53
B. AWS VPC
C. AWS S3
D. AWS EC2
The answer is: D
Q186. You can add ________________ to your Auto Scaling group so that you can perform custom actions when instances launch or terminate.
A. CloudWatch
B. CloudTrail
C. Load Balancer
D. Lifecycle Hooks
The answer is: D
Q187. What is Auto Scaling?
A. Accelerating VPC Speed
B. Creating/Terminating duplicate instances using Scale IN/OUT
C. Automating backup/restore service
D. None of the above
The answer is: B
Q188. You want complex querying capabilities but don’t want data warehouse. Which database service you would choose?
A. Amazon DynamoDB
B. Amazon Redshift
C. Amazon RDS
D. Amazon ElastiCache
The answer is: C
Q189. What is an Availability Zone?
A. A Container where all your S3 buckets are stored
B. Denotes an Entire Region
C. A location inside a Region which is protected from failures
D. Collection of Regions
The answer is: C
Q190. The cloud infrastructure is shared by several organizations and supports specific group that has shared concerns. Government departments, universities, central banks etc. often find this type of cloud useful. What kind of cloud deployment model is this?
A. Private Cloud
B. Hybrid Cloud
C. Community Cloud
D. Public Cloud
The answer is: C
Q191. How many Buckets you can create in S3?
A. 150
B. 250
C. 500
D. 100
The answer is: D
Q192. What is the maximum size of a S3 Bucket?
A. 3 Terabytes
B. 10 Terabytes
C. 5 Terabytes
D. 7 Terabytes
The answer is: C
Q193. Which service of Amazon AWS is used to host a static website?
A. Amazon Simple Storage Service(S3)
B. Amazon CloudFront
C. Amazon Route53
D. Amazon CloudWatch
The answer is: A
Q194. Which of the following is not a Part of Security groups?
A. List of Protocols
B. List of Users
C. Ports
D. IP Address
The answer is: B
Q195. A data transport solution that accelerates moving terabytes to petabytes of data into and out of AWS using storage devices designed to be secure for physical transport. Name this solution.
A. Amazon EFS
B. Amazon S3
C. Amazon Glacier
D. Amazon Snowball
The answer is: D
Q196. What type of IP address do you use for your CGW (Customer Gateway) address?
A. You will use PRIVATE IP address of your NAT device
B. You will use PUBLIC IP address of your NAT device
C. You will use ELASTIC IP address of your NAT device
D. You will use VPN
The answer is: B
Q197. How many subnets you can have per VPC?
A. 100
B. 300
C. 250
D. 200
The answer is: D
Q198. I have a REST API interface and uses secure HMAC-SHA1 authentication keys. I am also a data storage system. Who am I?
A. SS3
B. Elastic Block Store
C. S3
D. Snapshots
The answer is: C
Q199. I am a structured data store. I support indexing and data queries to both EC2 and S3. Who am I?
A. DynamoDB
B. SimpleDB
C. MySQL
D. Aurora
The answer is: B
Q200. How many Elastic IP address can be associated with a single account?
A) 4
B) 10
C) 5
D) None the above
Q201. After configuring ELB, you need to ensure that the user requests are always attached to a single instance. What setting can you use?
A) Session cookie
B) Cross one load balancing
C) Connection drainage
D) Sticky session
Q202. Which of the following metrics cannot have a cloud watch alarm?
A) EC2 instance status check failed
B) EC2 CPU utilization
C) RRS lost object
D) Auto scaling group CPU utilization
Q203. Which of the below mentioned service is provided by Cloud watch?
A) Monitor estimated AWS usage
B) Monitor EC2 log files
C) Monitor S3 storage
D) Monitor AWS calls using Cloud trail
Q204. Which of the following service provides the edge – storage or content delivery system that caches data at different locations?
A) Amazon RDS
B) Simple DB
C) Amazon Cloud Front
D) Amazon associates web services
Q205. What are the possible connection issues you can face while connecting to your instance?
A) Connection timed out
B) Server refused our key
C) No supported authentication methods available
D) All of the above
Q206. You are enabled sticky session with ELB. What does it do with your instance?
A) Routes all the requests to a single DNS
B) Binds the user session with a specific instance
C) Binds the user IP with a specific session
D) Provides a single ELB DNS for each IP address
Q207. Which is an email platform that provides an easy, cost effective way for you to send and receive email using your own email address and domains?
A) SES
B) SNS
C) SQS
D) SAS
Q208. AWS Cloud Front has been configured to handle the customer requests to the web server launched in Linux machine. How many requests per second can Amazon Cloud Front handle?
A) 1000
B) 100
C) 10000
D) There is no such limit
Q209. Which is virtual network interface that you can attach to an instance in a VPC?
A) Elastic IP
B) AWS Elastic Interface
C) Elastic Network Interface
D) AWS Network ACL
Q210. You have launched an instance in EC2-Classic and you want to make some change to the security group rule. How will these changes be effective?
A) Security group rules cannot be changed
B) Changes are automatically applied to all instances that are associated with the security group
C) Changes will be effective after rebooting the instance in that security group
D) Changes will be effective after 24-hours
Q211. Load Balancer and DNS service comes under which type of cloud service?
A) IAAS-Network
B) IAAS-Computational
C) IAAS-Storage
D) None of the above
Q212. You have an EC2 instance that has an unencrypted volume. You want to create another encrypted volume from this unencrypted volume. Which of the following steps can achieve this?
A) Just simply create a copy of the unencrypted volume, you will have the option to encrypt the volume.
B) Create a snapshot of the unencrypted volume and then while creating a volume from the snapshot you can encrypt it
C) Create a snapshot of the unencrypted volume (applying encryption parameters), copy the snapshot and create a volume from the copied snapshot
D) This is not possible, once a volume is unencrypted, there is no way to create an encrypted volume from this
Q213. Where does the user specify the maximum number of instances with the auto scaling commands?
A) Auto scaling Launch Config
B) Auto scaling group
C) Auto scaling policy
D) Auto scaling size
Q214. A user is aware that a huge download is occurring on his instance he has already set the auto scaling policy to increase the instance count when the network I/O increase beyond a certain limits how can the user ensure that this temporary event does not result in scaling
A) The network I/O are not affecting during data download
B) The policy cannot be set on the network I/O
C) There is no way the can stop scaling as it already configured
D) Suspend scaling
Q.215.Which are the types of AMI provided by AWS?
A) EBS Backed
B) Instance Store backed
C) None its volume type and not AMI types
D) Both A and B
Q 216. Name some cloud service providers for public & private cloud ?
Public: Amazon web services, Microsoft Azure, Google Cloud, Oracle Cloud, Alibaba Cloud.
Private: Redhat-Openstack, Rackspace, VMware, IBM Private Cloud.
Q 217. What are all the different Instance categories based on pricing and explain them briefly ?
On-demand Instances: On-demand instances are the virtual servers that are provisioned by AWS EC2 service at an hourly price basis.
Reserved Instances: Instances which are reserved for a time, 1 year or 3 years , is called reserved Instances. Hourly prices are reduced significantly compared to on-demand Instances with reservation.
Spot Instances: Spot Instances are the special instance category where you request the unused resources of EC2 from the datacenter for steep discounts. Spot prices are fixed by AWS EC2 and you need to bid the spot price more than the pricing of AWS EC2.
Q 218. I have some private servers on my premises, also I have distributed some of my workload on the public cloud, what is this architecture called ?
Hybrid Cloud
Q 219. What is the difference between S3 and Glacier storage ?
S3 is a simple storage service, which is used to store and retrieve data. We can store any amount of data and any type of data. Data that we are storing here are referred as objects. Whereas the Glacier storage is an archival store which is used to store infrequently accessed data or cold data. Major use case of glacier is data archiving and backup.
Q 220. Name some Database engines available natively in RDS services ?
MYSQL
MSSQL server
Oracle DB
Postgres DB
Amazon AURORA
Maria DB
Q 221. How can you automate resource provisioning in AWS ?
We can use the native service tool called AWS Cloud Formation for automation. It is also a good option to consider the third-party tools like Ansible, Chef, Puppet etc. to automate the services.
Q 222. What is autoscaling & mentions some of its benefits ?
Autoscaling is a service that automatically scales EC2 instance capacity out and in based on the criteria’s that we are going to set. Autoscaling benefits its use for dynamic workloads like web spikes, retail shop flash sales, ticket booking system on the vacations etc.,
Q 223. What is the difference between S3 availability & durability ?
Availability and durability are closely related to each other, but they are not the same. Availability refers to the uptime of the service i.e.., S3 storage system’s uptime and can able to deliver the requests and data. Durability on the other hand, refers to the data that is stored should not suffer from degradation and corruption.
Q 224. Mention some important features of S3 buckets ?
Static web hosting
Versioning
Encryption
Object lifecycle management
Unlimited storage
Q 225. What are all the measures that you take to protect the data in S3 ?
lists and pre-signed Encrypt the data using Server-Side Encryption or Client-Side Encryption.
Enable MFA delete to protect data against accidental deletion.
Usage of access control URL’s.
Q 226. What is Elastic IP address ?
Elastic IP address(EIP) is a static, internet routable address that is managed by the AWS platform. Each Elastic IP address are assigned to the Instances from a Pool of IP address in each region. Charges are applied once you allocate the EIP address no matter whether you associate the IP to an Instance or not. When you release the allocated IP Address, EIP will to returned to the pool.
Q 227. You have a webserver running on an Amazon EC2 instances that is approaching 100% CPU utilization. Which option will reduce load on the Amazon EC2 instance and describe why ?
We should create an Elastic load balancer with Autoscaling , and associate it with the EC2 instances. Layer 7 or Application layer Load balancers are used for this use case. ELB should be used because ELB can balance the incoming load across the EC2 resources.
Q 228.what is CloudWatch and mention what can we do with it ?
CloudWatch is native service used to monitor our resources and applications in the AWS cloud. CloudWatch does this by collecting information in the form of logs, metrics and events from the resources that we provisioned in the AWS environment. We can define alarms, troubleshoot issues using logs to optimize our infrastructure using CloudWatch.
Q 229.How will you classify the cloud, based on the services ?
We can classify the cloud computing platform into three types based on the services.
Infrastructure As A Service.
Platform As A Service.
Software As A Service.
Q 230.Name the messaging service available in AWS and point out a use case of it ?
Simple Notification Services is a complete messaging service to deliver the messages end to end. It is shortly referred to as SNS. A real time use case would be a banking system where SNS will be sending a real time message (Email, SMS etc.,) to the end users who debits his account by withdrawing some amount of money.
Q 231.Your company wants to use AWS for their newly designed analytics platform. They have got around 20 TB of data In the on-premises. They want to construct an analytics platform in AWS with this 20 TB of data for analysis. Once analysis is done they want to archive this data for best backup and recovery. What are the services that best matches this use case and say why ?
Redshift would be the proper analytics platform which AWS provides. For data storage S3 is the ideal option and once data analytics is done, data must get moved to glacier for backup & Archival system. To do this data migration from s3 to glacier wee need to setup a lifecycle management policy in S3 to get moved to glacier.
Q232.Your Relational database engine in AWS got crashes often when the traffic to your RDS instance is high. The Replica of the RDS instance is not promoted as master instance. What would you do to handle this situation ??
Under these circumstances, we need to choose a bigger RDS instance type for handling the huge amount of traffic. Creation of manual or automated snapshots is a must to recover from the disaster cases.
Q 233.There is a production DB server running in a EC2 Linux instance which has a ext4 formatted EBS volumes/disks attached. The database is about to run out of storage space. How can you address this problem ?
First, we need to increase the EBS volumes level to a consistent amount in the AWS management console. Next step we should use resize2fs command to use the provisioned space in the Operating system level because an increase in the EBS volumes doesn’t guarantee the increase in the OS level. For this to happen we should consider increasing the provisioned space in the operating system level.
Q 234.A company wants to migrate the on-premises servers to the AWS cloud platform. The company wants to estimate the cost of the machines that is going to get provisioned in the cloud. How would you proceed to determine the cost ?
Perform a mapping of the on-premises server’s cores and RAM to the nearest machine types in the AWS Cloud. Then use the online AWS pricing calculator to estimate the cost of the machines in the AWS Cloud.
Q 235. A XYZ company is using AWS services for the past one month for its production servers. They have established a VPN connectivity from on-premises to AWS with a single IPSEC tunnel. During peak production hours, servers are not reachable in the AWS Cloud due to network problem. How would you mitigate this problem with minimal cost ?
Considering the cost factor, we should first consider increasing the number if IPSEC tunnels that are used for the secure connectivity to AWS. If the problem persists even after increasing the tunnels, consider the other options for better a network.
Q236: What is the Cloud Computing?
Q237:What is merits of the Cloud Computing?
Totally free from Maintenance i.e., You do not have to maintain or administer any infrastructurefor the same.
Lower Computing Cost.
Improved Performance.
Reduced Software Cost.
Instant Software Updates.
Unlimited Storage Capacity i.e., It will never run out of the capacity, since it is virtually infinite.
Increased Data Reliability.
Device Independence and the “always on! Anywhere and any  of place” i.e., You can access your Cloud – based on  applications from anywhere, you just need a device which can connect to the Internet.Cloud Computing is the fastest growing part of  the network-based computing. It provides to tremendous.Benefits  to  customers of  the all sizes: simple users, developers, enterprises and all types of organizations.
Q238:What are the Cloud Computing?
Lower TCO.
Reliability, Scalability & Sustainability.
Secure Store Management.
Low Capital Expenditure.
Frees from Internal Resources.
Utility Based.
Easy & Agile Deployment.
Device & Location Independent.
24 * 7 Support.
Pay As You Use.
Q239:What are the top 10 advantages of Cloud Computing?
Pay as you Go Model.
Increased Mobility.
Less or No CAPEX.
High Availability.
Easy to Manage.
High Productivity.
Environment Friendly.
Less Deployment Time.
Dynamic Scaling.
Shared Resources.
Q240:What are the different layers (Service Models) of cloud computing?
Cloud computing consists of the  3 layers in the hierarchy and these are as follows:

Infrastructure as a Service (IAAS) provides cloud infrastructure in terms of the hardware like memory, processor speed etc.
Platform as a Service (PAAS) provides cloud applications platform for the developers.
Software as a Service (SAAS) provides cloud applications which is used by the user directly without Installing anything on the system.
Q241:How do disable Password-Based Logins for the Root in Amazon EC2 Instance?
Using a fixed for the root password for a public AMI is a security risk that can be quickly become known. Even Relying on users to change the password after to the first login opens a small window of  the opportunity for potential abuses.

Following are the steps to disable password-based on remote logins for the root users.

1.Open the /etc/ssh/sshd config  file with an text editor and locate to the following line:

#PermitRootLogin  yes.

2.Change to the line to:

PermitRoot Login without-password.

Q242:How can I take an Snapshot of a RAID Array?
Problem – Take an snapshot excludes data held in the cache by the applications and the OS. This tends not to matter on a single volume, however using a multiple volumes in the RAID Array, this can be a problem due to inter dependencies of  arrays.

Q243:What is the difference between Volume and Snapshot in the Amazon Web Services?
In Amazon Web Services, a Volume is  durables, block level storage can device that can be attached to a singles  EC2 instance. In plain words it is like an hard disk on which we can be write or read from.A Snapshot is created by copying the data of  volume to the another location at a specific time. We can even replicate samen of  Snapshot to multiple availability zones. So, Snapshot is the single point in time view of a volume. We can create an Snapshot only when we have a Volumes. Also, from a Snapshot we can create an Volumes. In AWS, we have to pay for the storage that is used by  Volume as well as the one used by a Snapshots.

Q244:What happens if my application to stops responding to requests in beanstalk?
AWS Beanstalk applications have an system in place for avoiding to failures in the underlying infrastructures.

Q245:How to update AMI tools at the Boot Time?
AWS is recommends that your AMIs downloads and upgrade to the Amazon EC2 AMI creation tools during the startup. This ensures that a new AMIs based on your shared AMIs have to the

latest AMI tools.

Q246:How to update AMI tools at the Boot Time on linux?
# Update to Amazon EC2 AMI tools

echo ” + Updating EC2 AMI tools”

yum update -y aws-amitools-ec2

echo ” + Updated EC2 AMI tools”

Q247:How does AWS Lambda to handle failure during event processing?
In AWS Lambda we can run a function of synchronous or asynchronous modes. In synchronous mode, if AWS Lambda function is fails, then it will just give on the exception to the calling application. In asynchronous  modes, if AWS Lambda function is fails then it will retry to  the same function at least 3 times. If AWS Lambda is running in response to an event in the Amazon DynamoDB or Amazon Kinesis, then  event will be retried till that Lambda function succeeds or the data expires. In DynamoDB or Kinesis, AWS maintains datas for at least 24 hours.

Q248:What are the Storage of classes of Amazon?
Amazon S3
Scalable Storage in Cloud
Amazon EBS
Block Storage for EC2
AWS Elastic File System
Managed File Storage for EC2
Amazon Glacier
Low-cost Achieve Storage in the
cloud
AWS Storage Gateway
Hybrid Storage Integration
Amazon Snowball
Petabyte-Scale Data Transport
AWS Snowball Edge
Petabyte-scale Data to Transport with
On-Demand Compute
AWS Snowmobile
Exabyte-scale Data to Transport
Q249:How do Encryption is done in S3?
In Transit: SSL/TLS
 At Rest
Server-Side in Encryption
S3 Managed Keys – SSE-S3
AWS Key Management Service, Managed of Keys – SSE-KMS
 6.Server-Side Encryption with Customer Provided Keys – SSE-C
Client-Side Encryptions
Q250:How will do upload a file greater than 100 megabytes in Amazon S3?
Amazon S3 supports of storing objects or files up to 5 terabytes. To upload an  file greater than 100 megabytes, we have to use of Multipart upload utility from AWS. By using Multipart upload we can upload an  large file in multiple parts. Each part will be independently to be uploaded. It doesn’t matter in what order to each part is uploaded. It even to supports uploading these parts of  parallel to decrease overall time. Once of all the parts are uploaded, this utility makes a these as one single objects or file from which the parts were do created.
