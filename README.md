# CIL-Assignment-1

## Description
A repo for my first CIL Cloud Engineering Assignment

# Problem Statement

- Create a CloudFormation (CFN) stack that launches a t2.micro EC2 instance (Amazon Linux 2 AMI)
and an S3 bucket.
- Give the EC2 instance a role that allows it to be accessed via the Session Manager (SSM) instead
of via SSH with key-pairs.
- Set up the EC2 instance to act as a backup for images uploaded to the S3 bucket. The backup should be done
to a folder `/home/user/myS3backup`.
- Write a python script that copies the S3 content to the backup directory
- Set up a cronjob that runs the python script at least once every day at any time of choice.

# Architectural Diagram
![arch.png](snapshots/Arch-Snapshot.png)

> ## Cloud Formation
> CloudFormation is an AWS service that allows users to define and provision AWS infrastructure resources using declarative JSON or YAML templates.
> This allows the infrastructure to be treated as code which can be shared between developers and can be versioned and stored using 
Version Control Systems (VCS).

> ## EC2 
> Amazon Elastic Compute Cloud (EC2) provides compute capacity for users and other services in the AWS Cloud. It is a virtual machine
> which can be provisioned with various operating systems and compute capacities as required. 

![img.png](Instance.png)

> ## IAM Role
> An IAM Role is an AWS Identity that has permissions to perform specific actions. It is similar to an IAM User but is not uniquely associated with one
> person. Instead, is it intended to be assumable by anyone or any services that needs to perform the actions the role allows.

![img.png](Roles.png)

> ## S3
> AWS Simple Storage Service (S3) is an object storage service.

![img.png](S3.png)

> ## Python Script
> The python script was written using the AWS SDK for python (Boto3).


![img.png](Python-file.png)

> ## Cron
> The python script was scheduled as 
> 0 5 7 * * * python3 newfile.py`. Which means it'll run at 5 minute intervals during the 7th hour every day, month and day of the week
