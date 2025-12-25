<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Testing VPC Connectivity

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-connectivity)

**Author:** Aaron  
**Email:** Justaaron1981@yahoo.com

---

## Testing VPC Connectivity

![Image](http://learn.nextwork.org/gleeful_red_proud_durian/uploads/aws-networks-connectivity_8ee57662)

---

## Introducing Today's Project!

### What is Amazon VPC?

It is Amazon's foundational networking service. Having VPC is the reason why our resources can be made private or public to the internet. we also set up our own traffic, security rules with in the VPC 

### How I used Amazon VPC in this project

I used amazon VPC's a VPC structure and components using the VPC wizard, then launched EC2 instances and tested the connectivity between my network's resources

### One thing I didn't expect in this project was...

I didn't expect to run into an error due to a network ACL's source pointing to an incorrect subnet CIDR block.

### This project took me...

two hours and thirty minutes 

---

## Connecting to an EC2 Instance

connectivity means getting resources in our network to communicate with each other, and how well they can communicate/deliver data to each other. Without connectivity, resources in our network can not communicate e.g. users can't access our application

My first connectivity test was whether I could connect to my Nextwork public server (an EC2 instance)

![Image](http://learn.nextwork.org/gleeful_red_proud_durian/uploads/aws-networks-connectivity_88727bef)

---

## EC2 Instance Connect

I connected to my EC2 instance using EC2 Instance Connect, which is a tool provided by Amazon EC2 that allows us to directly access an EC2 instance using the AWS management console we no longer need to manage key pairs or use an SSH client to get access to connect to our EC2 instance

My first attempt at getting direct access to my public server resulted in an error, because my private server had a security group that did not allow SSH traffic it only allowed HTTP traffic 

I fixed this error by adding a new inbound rule in my Nextwork private servers security group that allows traffic from anywhere

![Image](http://learn.nextwork.org/gleeful_red_proud_durian/uploads/aws-networks-connectivity_1cbb1b88)

---

## Connectivity Between Servers

Ping is a tool to test the connectivity between two servers and the response times. I used ping to test the connectivity between i used ping to test the performance between my private and public servers

The ping command I ran was 'ping 10.0.1.215', which is the private ipv4 address of my private server

The first ping returned no replies from the private server. This meant security settings with my private server were blocking inbound and/or outbound ICMP traffic. Which is the traffic type of ping messages.

![Image](http://learn.nextwork.org/gleeful_red_proud_durian/uploads/aws-networks-connectivity_defghijk)

---

## Troubleshooting Connectivity

I troubleshooted this by enabling ICMP in my private  server's network ACLs and security groups. As a bonus, I also made sure the source I defined pointed to my public subnet. identified in my network ACL to my public subnet.


![Image](http://learn.nextwork.org/gleeful_red_proud_durian/uploads/aws-networks-connectivity_4a9e8014)

---

## Connectivity to the Internet

Curl is a connectivity tool that test connectivity from one server to another server and retrieves data from the target server too

I used curl to test the connectivity between my network's public server and the public internet. This test would only be successful internet gateway, network ACLs, security groups, and route tables were set up correctly 

### Ping vs Curl

'Ping and curl are different because they give different responses to public servers terminal. Ping- responeses with a report on performance of connectivity with my private server. Curl responded with HTML data from another public server.

---

## Connectivity to the Internet

I ran the curl command  curl https://learn.nextwork.org/projects/aws-networks-connectivity?utm_source=marketing-app which returned HTML content of  Nextwork's first project guide





![Image](http://learn.nextwork.org/gleeful_red_proud_durian/uploads/aws-networks-connectivity_8ee57662)

---

---
