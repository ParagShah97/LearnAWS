# AWS

## IAM (Identity Access Management)

#### Roles
We can create roles with required permission, for example *IAMReadOnly* and we can attach it to EC2 instance this will allow us to use IAM command in EC2 SSH connect, without
manually providing the credentials on the shell.

## EC2 Basics (Elastic compute cloud) - IAAS Infrastructure as a Service

* Storing data on virtual drives (EBS)
* Distribute load across machines (ELB)
* Scaling the services using an auto-scaling group (ASG)

#### Points to remember
Upon restarting EC2 instance the public IP will change. Though the private IP remain the same.

### Security Group
Fundamental of network security in AWS.
Controls how traffic is allowed into or out of EC2 instances.
Only contain *allow* rules.
It will acts like a firewall.
**It's good to maintain on seperate security group for SSH access**

#### Classic Ports to know

- 22 = SSH (Secure Shell) - log into a Linux instance
- 21 = FTP (File Transfer Protocol) – upload files into a file share
- 22 = SFTP (Secure File Transfer Protocol) – upload files using SSH
- 80 = HTTP – access unsecured websites
- 443 = HTTPS – access secured websites
- 3389 = RDP (Remote Desktop Protocol) – log into a Windows instance

## EBS Elastic block Storage (network drive)
EBS volume is a network drive you can attach to your instances while they run. Allows your instances to persist data even after their termination. 
Can be mounted to one instance at a time at CCP level.
Locked to an availability zone(AZ) for example EBS volume in us-east-1a cannot be attached to us-east-1b, need to snapshot it to move a volume across.

One EBS cannot attach to 2 EC2 instances whereas 2 EBS can attach to single EC2 instance.
**Exception**: For EBS io1/io2 family same EBS volume can attach to multiple EC2 instances (But only possible for 1 AZ instances) (Upto 16 instances at a time).

### EBS Volumes Types:
* gp2 / gp3 SSD: Balanced Price and performance.
* io1/io2 Block Express (SSD): Highest Perfromance SSD (Good for low latency task).
* st 1 (HDD): Low cost, frequently accessed.
* sc 1 (HDD): Lowest cost, less frequently accessed.

  Only gp2 / gp3 SSD and io1/io2 Block Express (SSD) can be used as Boot volumnes. (Where root OS will store)

## AMI Amazon Machine Image (Region Sepcific)
Customization of an EC2 instance, you can add your software, configuration,and others.
Types of AMI to launch EC2 instance:
A Public AMI
Your own AMI
An AWS Marketplace AMI

## EFS Elastic File System
It is a Managed NFS (netwrk file system), a centralized system. Highly available, high performance.
Only Compatable with Linux based AMI not with windows.
Multipe EC2 instances from varios region can connect to the same EFS.





