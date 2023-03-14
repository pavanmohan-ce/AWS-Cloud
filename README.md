# Cloud
 Cloud computing is the delivery of computing resources such as servers, storage, databases, networking, software, analytics, and intelligence over the Internet ("the cloud") to offer faster innovation, flexible resources, and economies of scale.

<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRz0AhTRLpnCAPdsMz7ntki-p4k_-ph7PPnmlM0W8L9oUkbO35m_VGgHiS4V1ynDGzGNeo&usqp=CAU" width="90" ><img src="https://www.openbravo.com/blog/wp-content/uploads/2020/03/azure-cloud.jpg" width="90" ><img src="https://camo.githubusercontent.com/f206c21f72582e8e173941e2ebde4bd231b4a91ef1763991aecb79f7bb4566ba/68747470733a2f2f692e6962622e636f2f546271355337312f6763702e706e67" width="90" >



#### There are three main types of cloud services:

   - **Infrastructure as a Service** (IaaS): In this model, the cloud provider offers virtualized computing resources, such as servers, storage, and networking. Customers can use these resources to build and deploy their own applications and services. Examples of IaaS providers include Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP).

   - **Platform as a Service** (PaaS): This model provides a platform for customers to build, deploy, and manage their own applications without having to worry about the underlying infrastructure. PaaS providers offer a complete development and deployment environment, including development tools, databases, and middleware. Examples of PaaS providers include AWS Elastic Beanstalk, Microsoft Azure App Service, and Heroku.

   - **Software as a Service** (SaaS): In this model, the cloud provider offers fully-managed applications that customers can use over the internet. Customers do not need to manage the underlying infrastructure or software, and can simply access the application through a web browser or other client. Examples of SaaS providers include Salesforce, Dropbox, and Google Workspace.

#### There are three main types of cloud platforms:

   - **Public Cloud**: These platforms are owned and operated by third-party providers, such as AWS, Microsoft Azure, and GCP. Customers can access these platforms over the internet and pay for the resources they use.

   - **Private Cloud**: These platforms are owned and operated by an individual organization or a third-party provider on behalf of the organization. Private cloud platforms are typically used by organizations that have strict security and compliance requirements.

   - **Hybrid Cloud**: These platforms combine public and private cloud services, allowing customers to use both on-premises and cloud resources to build and deploy their applications. Hybrid cloud platforms can provide greater flexibility and scalability than either public or private cloud platforms on their own.

# AWS <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/93/Amazon_Web_Services_Logo.svg/800px-Amazon_Web_Services_Logo.svg.png" width="60" >

 *AWS* (Amazon Web Services) is a cloud computing platform offered by Amazon. It provides a wide range of cloud-based computing services, including computing power, storage, database management, analytics, machine learning, security, and more. AWS allows businesses and organizations to quickly and easily access the computing resources they need on a pay-as-you-go basis, without having to invest in expensive hardware or infrastructure.



## 1 KMS (Key Management Service) :
> *KMS* is a fully managed service that helps you create and control encryption keys to protect your data in AWS services and in your own applications. KMS provides a highly available key storage, management, and auditing solution for your encryption keys. You can use KMS to encrypt data stored in Amazon S3, Amazon EBS, Amazon RDS, and other AWS services. You can also use KMS to encrypt data in your own applications, and to control the access to the encryption keys themselves.

- #### Create an Encryption Key with KMS:
	#####   Go to the AWS Management Console and open the KMS console.
	<img src="https://www.jscape.com/hs-fs/hubfs/Using%20AWS%20KMS%20To%20Encrypt%20Files%20You%20Upload%20To%20Your%20S3%20Trading%20Partner%20-%20kms%20service.png?width=837&name=Using%20AWS%20KMS%20To%20Encrypt%20Files%20You%20Upload%20To%20Your%20S3%20Trading%20Partner%20-%20kms%20service.png" width="500" height="250">
	
	#####  Click on "Create key" button and follow the prompts to create a new KMS encryption key.
	<img src="https://blogs.halodoc.io/content/images/2020/12/Screenshot-2020-11-04-at-11.42.04-AM.png" width="500" height="250">
	
	#####  Choose the appropriate key policy and set permissions for the key.
	<img src="https://docs.incorta.com/static/23dcb29490b083799b66bdc2095dfd6e/d67fd/aws_image29.png" width="500" height="250">
	
	#####  Once the key is created, copy the ARN for the key. You will need this ARN later to associate the key with an EC2 instance.
	<img src="https://docs.aws.amazon.com/images/kms/latest/developerguide/images/console-key-detail-view-symmetric-sm.png" width="630" height="300">

## 2 Security Groups:
> A *security group* acts as a virtual firewall for your EC2 instances to control incoming and outgoing traffic. You can use security groups to specify inbound and outbound rules that allow traffic from specific IP addresses, protocols, and ports. You can also use security groups to restrict traffic to specific security groups, which can help you enforce security policies and protect your applications and data.

****Inbound rules**** are used to allow or block incoming traffic to your resource.

****Outbound rules**** are used to allow or block outgoing traffic from your resource.

- #### Create a Security Group:
	##### Go to the AWS Management Console and open the EC2 console at https://console.aws.amazon.com/ec2/
	<img src="https://res.cloudinary.com/practicaldev/image/fetch/s--zz2eYbRC--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/rv4yanm70lsvwesa02ww.png" width="500" height="250">
	
	##### Click on "Security Groups" on the left-hand side menu and then click on "Create Security Group".
	<img src="https://www.howtogeek.com/wp-content/uploads/csit/2021/06/3fa1d51d.png?trim=1,1&bg-color=000&pad=1,1" width="500" height="250">

	##### Give the security group a name and description.
	<img src="https://cloudacademy.com/wp-content/uploads/2015/11/Picture1-1.png" width="500" height="250">
	
	##### Add inbound rules to allow traffic only on necessary ports. 
	For example, if you are setting up a web server, you may want to allow traffic on ports 80 and 443.
	<img src="https://i.stack.imgur.com/jws1t.png" width="500" height="250">
	
	##### Associate the security group with your EC2 instance.
	<img src="https://static.javatpoint.com/tutorial/aws/images/aws-security-group5.png" width="500" height="250">
	
## 3 SSH keys:
> *SSH* keys are used for secure remote access to your EC2 instances. SSH keys are generated in pairs – a public key and a private key. You upload the public key to your EC2 instances, and then use the corresponding private key to authenticate when you connect to the instances via SSH.

- ### Create an SSH key pair in AWS:

   ##### Open the Amazon EC2 console at https://console.aws.amazon.com/ec2/
   <img src="https://docs.aws.amazon.com/images/ground-station/latest/ug/images/ssh-keypair.png" width="500" height="250">
   
   ##### Choose "Create Key Pair."
   <img src="https://leaherb.com/wp-content/uploads/AWS_Console_Key_Pairs.png" width="500" height="250">
   
   ##### Enter a name for your key pair in the "Key pair name" field and choose the file format for your private key and select "Create Key Pair."
   The most common format is "PEM."
   
   <img src="https://www.how2shout.com/linux/wp-content/uploads/2021/08/Create-SSH-ec2-Key-Pair.png" width="500" height="250">
   
   ##### The private key file will automatically download to your computer. Save the private key file to a secure location.
   <img src="https://www.ktexperts.com/wp-content/uploads/2020/10/3-7.png" width="500" height="250">
   
## 4 EC2 Instances: 
 > *Amazon Elastic Compute Cloud* (EC2) is a web service that provides resizable compute capacity in the cloud. EC2 instances are virtual servers that run on Amazon's cloud infrastructure.

- **Amazon EC2** provides a wide range of instance types optimized to fit different use cases. Each instance type is designed to offer a specific combination of CPU, memory, storage, and networking capacity. 
 	- **General Purpose**: These instances provide a balance of compute, memory, and networking resources and are suitable for a variety of workloads such as web servers, small and medium databases, and enterprise applications. Some examples of general purpose instance types are t3, m5, and a1.

    - **Compute Optimized**: These instances provide high compute power and are suitable for compute-intensive workloads such as batch processing, scientific modeling, and high-performance computing. Some examples of compute optimized instance types are c5 and c6g.

   - **Memory Optimized**: These instances provide high memory capacity and are suitable for memory-intensive workloads such as big data processing, in-memory databases, and real-time analytics. Some examples of memory optimized instance types are r5 and x1.

   - **Storage Optimized**: These instances provide high storage capacity and are suitable for storage-intensive workloads such as NoSQL databases, data warehousing, and Hadoop clusters. Some examples of storage optimized instance types are i3 and d2.

   - **Accelerated Computing**: These instances provide specialized hardware such as GPUs and FPGAs and are suitable for compute-intensive workloads such as machine learning, graphics rendering, and video encoding. Some examples of accelerated computing instance types are p3 and g4.

   
 ### Volumes: 
> Amazon EC2 provides two types of volumes - Amazon Elastic Block Store (EBS) volumes and instance store volumes. 
 - **EBS** volumes provide persistent block-level storage that can be attached to EC2 instances. 
 - Instance store volumes provide temporary block-level storage that is physically attached to the host machine.

### AMIs: 
> *Amazon Machine Images* (AMIs) are pre-configured virtual machines that contain an operating system, application server, and applications. You can use these images to launch EC2 instances. Amazon provides a variety of public AMIs for popular operating systems and software stacks, or you can create your own custom AMIs.

### Snapshots: 
> *Amazon snapshots* are point-in-time copies of EBS volumes. You can use snapshots to create new EBS volumes, or to restore an existing EBS volume to a previous state. Snapshots are stored in Amazon S3 and are highly durable and scalable.


### Elastic IPs: 
> An *Elastic IP* is a static, public IP address that you can allocate to your account and assign to an instance. This IP address can be remapped to another instance if needed.



## The steps to create an EC2 instance, connect to it with SSH, and install various packages:

###  Step 1: Create an EC2 Instance

   ##### Go to the Amazon EC2 console at https://console.aws.amazon.com/ec2/.
   <img src="http://res.cloudinary.com/dyd911kmh/image/upload/f_auto,q_auto:best/v1511519108/2_ClickonEC2_Red_tkujys.png" width="500" height="250">
   
   ##### Click on the "Launch Instance" button.
   <img src="https://k21academy.com/wp-content/uploads/2020/12/1-68.png" width="500" height="250">
   
   ##### Choose an Amazon Machine Image (AMI) for your instance. This is the software that will run on your instance.
   <img src="https://static.javatpoint.com/tutorial/aws/images/aws-security-group.png" width="500" height="250">
   
   ##### Choose an instance type. This determines the hardware resources that will be allocated to your instance.
   <img src="https://static.javatpoint.com/tutorial/aws/images/aws-security-group1.png" width="500" height="250">
   
   ##### Configure your instance details. This includes the number of instances to launch, network settings.
   <img src="https://static.javatpoint.com/tutorial/aws/images/aws-security-group2.png" width="500" height="250">
   
   ##### Attach the EBS Volume to your EC2 instance.
   <img src="https://static.javatpoint.com/tutorial/aws/images/aws-security-group3.png" width="500" height="250">
    
   ##### Add tags to your instance (optional).
   <img src="https://static.javatpoint.com/tutorial/aws/images/aws-security-group4.png" width="500" height="250">
   
   ##### Configure security groups. This determines the inbound and outbound traffic that is allowed to your instance.
   <img src="https://static.javatpoint.com/tutorial/aws/images/aws-security-group5.png" width="500" height="250">
   
   ##### Review your instance details and launch the instance.
   <img src="http://res.cloudinary.com/dyd911kmh/image/upload/f_auto,q_auto:best/v1511519109/6_ReviewInstanceLaunch_Red_ugndox.png" width="500" height="250">
   
   ##### Create a key pair if you don't have one already. This is used to securely connect to your instance.
   <img src="https://static.javatpoint.com/tutorial/aws/images/aws-security-group8.png" width="500" height="250">

###  Step 2: Connect to EC2 with SSH

   - Open a terminal window on your local machine.
   - Navigate to the directory where your key pair is stored.
   - Set the permissions on your key pair file with the command ``` chmod 400 your_key_pair.pem ```.
   - Connect to your instance with the command ``` ssh -i your_key_pair.pem ec2-user@your_instance_public_ip_address ```.

###  Step 3: Install Various Packages

Once you have connected to your instance, you can install various packages using the package manager for your operating system. For example, if you are using Amazon Linux 2, you can use the yum package manager.

###### Here are some example commands to install various packages:

Install Apache web server: 
    
    
    sudo yum install httpd 
     
Install MySQL: 
    
    
    sudo yum install mysql-server 
Install Git: 
    
    
    sudo yum install git 
    

## The steps to create a snapshot from the root volume of an EC2 instance and create a custom AMI from the snapshot:

### Step 1: Create a Snapshot

   - Go to the Amazon EC2 console at https://console.aws.amazon.com/ec2/.
   - Select the instance volume for which you want to create a snapshot.
   - From the "Actions" dropdown menu, select "Create Snapshot".
   - In the "Create Snapshot" dialog box, enter a name and description for the snapshot.
   - Click on the "Create Snapshot" button.

### Step 2: Create a Custom AMI from the Snapshot

   - In the EC2 console, select the snapshot you just created.
   - From the "Actions" dropdown menu, select "Create Image".
   - In the "Create Image" dialog box, enter a name and description for the AMI.
   - Choose the instance type that you want to use for the AMI.
   - Choose the root device volume and the snapshot you just created.
   - Configure any additional settings for the AMI, such as IAM roles or tags.
   - Click on the "Create Image" button.


## The steps to create an EC2 instance from the custom AMI that you created in the previous question:

   - Go to the Amazon EC2 console at https://console.aws.amazon.com/ec2/.
   - Click on the "Launch Instance" button.
   - In the "Step 1: Choose an Amazon Machine Image (AMI)" section, click on the "My AMIs" tab.
   - Select the custom AMI that you have created previously from the list of available images.
   - Choose an instance type for your instance.
   - Configure your instance details, such as the number of instances to launch, network settings, and storage options.
   - Add any additional tags or user data for your instance.
   - Configure security groups to allow inbound and outbound traffic.
   - Review your instance details and click on the "Launch" button.
   - Select an existing key pair or create a new one to securely connect to your instance.
    
 ## The steps to configure your local .ssh/config file to connect to remote EC2 instances:

   - Open a terminal window on your local machine.
   - Navigate to your home directory by typing cd ~.
   - Create a new .ssh directory by typing mkdir .ssh.
   - Change the permissions on the .ssh directory by typing chmod 700 .ssh.
   - Navigate to the .ssh directory by typing cd .ssh.
   - Create a new file named config by typing touch config.
   - Open the config file with a text editor, such as nano or vim.
   - Add a new section for the remote EC2 instance that you want to connect to, using the following format:
   ```
   Host demo
    User                   <username> 
    HostName               <Public DNS or IP Address of your instance>
    Port                   22
    IdentitiesOnly         yes
    IdentityFile           </path/to/your/private/key>
    UserKnownHostsFile     /dev/null
    StrictHostKeyChecking  no
    PasswordAuthentication no
    TCPKeepAlive           yes
   ```
   - Save and close the config file.
   - Set the permissions on the config file by typing chmod 600 config.
   
  You can now connect to the remote EC2 instance by typing ssh demo in the terminal, where demo is the name you chose for this remote host in the config
  
  ## NACL 
  
  <img src="https://i.ytimg.com/vi/tLAgYQlMWGo/maxresdefault.jpg" width="500" height="250">
 
 > - Network Access Control List is a security feature offered by AWS (Amazon Web Services) that helps to control traffic to and from your instances in a VPC (Virtual Private Cloud). NACLs are stateless, meaning that they apply to inbound and outbound traffic separately.

> - NACLs are similar to a firewall, but they operate at the subnet level rather than at the instance level. This means that a single NACL can be used to control traffic for multiple instances within a subnet. NACLs allow you to create rules that allow or deny traffic based on IP addresses, port numbers, and protocols.

> - When traffic enters a subnet, AWS applies the NACL rules in the inbound order to determine whether to allow or deny the traffic. When traffic leaves a subnet, AWS applies the NACL rules in the outbound order. If a rule in the inbound or outbound direction denies traffic, then that traffic is dropped and not forwarded.
