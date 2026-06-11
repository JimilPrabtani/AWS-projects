<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Virtual Private Cloud

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-vpc)

**Author:** Jimil Prabtani  
**Email:** jimilprabtani0816@gmail.com

---

## Build a Virtual Private Cloud (VPC)

![Image](http://learn.nextwork.org/affectionate_green_mysterious_penguin/uploads/aws-networks-vpc_2facf927)

---

## Introducing Today's Project!

In this project, I will demonstrate how to deploy VPC with a public subnet and how it can communicate to the internet using a gateway. I'm doing this project to learn AWS cloud services.

### What is Amazon VPC?

Amazon VPC is a private cloud inside of a large public cloud. and it is useful because e can isolate our resources fron the public access and the internet .

In today's project, I used Amazon VPC to launch EC2 instance in a private environment and also attached internet gateway to the there is internet connectivity from the public subnet.

### Personal reflection

This project took me around 1 hour, because I was using the EC2 instance to set-up ollama and openclaw together. 

One thing I didn't expect in this project was that there was already a VPC in the region and there is one default VPC in every region so that we can create resources seemlessly from the begineing.

---

## Virtual Private Clouds (VPCs)

### What I did in this step

In this step, I will create VPC using AWS console. because we need a private environment where we can deploy and setup our resources.

### How VPCs work

VPCs are private cloud as the name suggests virtual private cloud inside of a huge AWS region which is public and it is used for isolating of the resourses from the public network.

### Why there is a default VPC in AWS accounts

There was already a default VPC in my account ever since my AWS account was created. This is why we have been able to deploy resources like EC2 instances and connect services together fron the DAY 1 if using AWS. If there was no default VPC provisined in the AWS account I would've had to learn how to create a VPC before I could use some of the services that need a VPC to finction.

![Image](http://learn.nextwork.org/affectionate_green_mysterious_penguin/uploads/aws-networks-vpc_2facf927)

### Defining IPv4 CIDR blocks

To set up my VPC, I had to define an IPv4 CIDR block, which is Classless inter-Domain Routing it means dividing/segmenting the main network into smaller chunks to assign a group of IP addresses to the resources.

---

## Subnets

### What I did in this step

In this step, I will create a subnet inside of our main network. So, that we can Utilize it to create resources that can be segments as public and private.

### Creating and configuring subnets

Subnets are the sub-divisions of the main network that helps us to segment the network. There are already subnets existing in my account, one for every AZ-Availablity Zone.

### Public vs private subnets

The difference between public and private subnets are public subnet is used communicate to the external resources and private subnet containes resources that are isolated and cannot be reached through internet. For a subnet to be considered public, it has to have connectivity to hte internet through internet gateway.

![Image](http://learn.nextwork.org/affectionate_green_mysterious_penguin/uploads/aws-networks-vpc_157c4219)

### Auto-assigning public IPv4 addresses

Once I created my subnet, I enabled Auto-assign public IPv4 address. This setting makes sure that can resources that are deploy inside this subnet will get a public IP address automatically without any manual effort. so that we cna save time.

---

## Internet gateways

### What I did in this step

In this step, I will create internet gateway. This is important because this is like building a bridge (internet gateway) that links your private city (VPC) to the outside world (the internet), so your resources can communicate beyond your private space. 

### Setting up internet gateways

Internet gateways connects your city (VPC) and the outside world (internet).

Internet gateways are key to making applications available on the internet. By attaching an internet gateway, your instances can access the internet and be accessible to external users.

Attaching an internet gateway to a VPC means resources in your VPC can now access the internet. The EC2 instances with public IP addresses also become accessible to users, so your applications hosted on those servers become public too. If I missed this step the recources can't communitcate to the internet from the public subnet.

![Image](http://learn.nextwork.org/affectionate_green_mysterious_penguin/uploads/aws-networks-vpc_4ae90410)

---

## Using the AWS CLI

### What I'm doing in this extension

In this project extension, I will deploying VPC using AWS CLI commands. because it was a faster, more efficient way to do this project.

### Exploring CloudShell and CLI

### Debugging my setup

To set up a VPC or a subnet, you can use the command "aws ec2 create-vpc --cidr-block 20.0.0.0/24 --query Vpc.VpcId --output text" and to add the name to the vpc you can use this command "aws ec2 create-tags --resources=VPC-ID --tags Key=Name,Value="NextWork-project-VPC 2" ".  Make sure to avoid errors by replacing the VPC-ID with your actual vpc id that can be seen on the vpc dashboard.

![Image](http://learn.nextwork.org/affectionate_green_mysterious_penguin/uploads/aws-networks-vpc_9b2465411)

### Comparing CloudShell vs AWS Console

Compared to using the AWS Console, an advantage of using commands is that it is faster and clean. An advantage of using the Console is we can deploy multiple resources in seconds without clicking buttons. Overall, I preferred the dashboard to created the resources beacuse I'm new to the AWS cli.

---

---
