# Internet Protocols - Public and Private IP Addresses

## Lab Overview

This lab focused on understanding the difference between public and private IPv4 addresses and applying these concepts to troubleshoot an AWS networking scenario.

The scenario involved two EC2 instances located in the same VPC and subnet. Instance A could not be accessed from the internet, while Instance B could. The investigation focused on identifying the difference in their IP addressing.

The lab also introduced a customer scenario involving a proposed public CIDR range for a new VPC and required an assessment of whether using public address space would be appropriate.

## Objectives

* Investigate an AWS customer networking scenario.
* Understand the difference between public and private IPv4 addresses.
* Troubleshoot EC2 connectivity using SSH.
* Understand why an EC2 instance may require a public IP for direct internet access.
* Understand the purpose of private CIDR ranges within a VPC.
* Evaluate the use of public versus private IPv4 address space.
* Apply networking concepts to a practical AWS troubleshooting scenario.

## Environment

* Amazon VPC
* Amazon EC2
* Amazon Linux 2
* SSH
* IPv4 addressing
* Private and public IP addresses
* CIDR notation

## Customer Scenario

The customer had an existing VPC using the CIDR range:

10.0.0.0/16

The VPC contained two EC2 instances:

* Instance A could not be reached from the internet.
* Instance B could be reached from the internet.
* Both instances were located in the same VPC and subnet.
* The existing routing configuration was already correctly configured.

The customer also asked whether they could use the public CIDR range:

12.0.0.0/16

for a new VPC.

Because the routing configuration was already correct, the investigation focused on comparing the IP addresses assigned to the two EC2 instances.

## Investigation

The networking configuration of both EC2 instances was inspected to compare their private and public IPv4 addresses.

The key difference was:

* **Instance A:** Had only a private IP address.
* **Instance B:** Had both a private IP address and a public IP address.

This demonstrated that an EC2 instance can communicate within the VPC using its private IP while also using a public IP for internet-facing connectivity.

## SSH Connectivity Test

Before testing the instances, the permissions of the SSH private key were restricted:

chmod 400 labsuser.pem

### Instance A

Instance A was tested using its private IP address:

ssh -i labsuser.pem ec2-user@10.0.10.164

The connection timed out:

ssh: connect to host 10.0.10.164 port 22: Operation timed out

This was expected because 10.0.10.164 is a private IP address and cannot be directly reached from the public internet.

### Instance B

Instance B was then tested using its public IP address:

ssh -i labsuser.pem ec2-user@54.187.194.84

The SSH connection succeeded and provided access to the Amazon Linux instance:

[ec2-user@ip-10-0-10-30 ~]$

This confirmed that Instance B had the public IP addressing required for direct internet-facing SSH connectivity, assuming the relevant routing and security controls allowed the connection.

## Key Findings

### Private IP Addresses

Private IPv4 addresses are used for communication within private networks such as an AWS VPC.

A private IP address is not directly routable over the public internet.

Instance A only had a private IP address, which explained why an SSH connection from the local computer using that address failed.

Private addressing is useful for internal communication between AWS resources, such as EC2 instances communicating with other resources inside the VPC.

### Public IP Addresses

A public IPv4 address provides an internet-facing address for an AWS resource.

Instance B had both:

* Private IP: 10.0.10.30
* Public IP: 54.187.194.84

The private IP is used for communication within the VPC, while the public IP can be used to communicate with the instance from the internet when the surrounding AWS networking and security configuration permits it.

It is important to distinguish between assigning a public IP to an EC2 instance and using a public CIDR range for an entire VPC. These are separate concepts.

## VPC CIDR Ranges

The customer's existing VPC used:

10.0.0.0/16

This is part of the RFC 1918 private IPv4 address space and is appropriate for internal VPC addressing.

The customer proposed:

12.0.0.0/16

This is public IPv4 address space rather than RFC 1918 private address space.

Using public address space for internal VPC addressing is generally not recommended because the addresses could overlap conceptually with resources that exist on the public internet. This can create routing and connectivity complications.

A private RFC 1918 range should therefore normally be used for VPC CIDRs.

Common RFC 1918 private IPv4 ranges include:

* 10.0.0.0/8
* 172.16.0.0/12
* 192.168.0.0/16

## VPC CIDR vs EC2 IP Address

The lab reinforced that the VPC CIDR and an EC2 instance's IP addresses serve different purposes.

* **VPC CIDR:** Defines the private IPv4 address space available within the VPC.
* **EC2 private IP:** Identifies the instance within the VPC.
* **EC2 public IP:** Provides an internet-facing address for the instance.

A simplified example is:

VPC
10.0.0.0/16
|
+-- EC2 Instance B
|
+-- Private IP: 10.0.10.30
|
+-- Public IP: 54.187.194.84

This demonstrates how a VPC can use a private CIDR range while an individual EC2 instance can have a public IP address.

## SSH and TCP

The lab also reinforced the relationship between SSH and TCP.

* **SSH:** An application-layer protocol used for secure remote administration.
* **TCP:** A transport-layer protocol that provides reliable communication.
* **TCP Port 22:** The standard port used by SSH.

The relationship can therefore be simplified as:

SSH → TCP → IP

SSH is not a replacement for TCP and is not itself a method of accessing the internet. SSH is an application protocol that uses TCP to establish a reliable network connection.

## Troubleshooting Approach

The lab demonstrated an important networking troubleshooting process.

When one EC2 instance can be reached but another cannot, compare the working and non-working configurations.

The investigation considered:

1. Whether the instances were in the same VPC and subnet.
2. Whether the routing configuration was correct.
3. Whether the instances had private or public IP addresses.
4. Whether SSH was being attempted against the correct IP address.
5. Whether the relevant security controls would permit SSH traffic.
6. Whether the address being used was reachable from the network where the SSH connection originated.

In this scenario, the key difference was the IP addressing of the two instances.

## Final Outcome

The customer's connectivity issue was identified as an IP addressing difference between the two EC2 instances.

* **Instance A** had only a private IP address and therefore could not be directly accessed from the internet using SSH.
* **Instance B** had both a private and public IP address and could be accessed using SSH through its public IP.
* The VPC's existing CIDR range of 10.0.0.0/16 was an appropriate private IPv4 range.
* The proposed 12.0.0.0/16 range was public address space and was not recommended for internal VPC addressing.
* The lab demonstrated the difference between a public IP assigned to an individual EC2 instance and the CIDR range used to address resources within a VPC.

## Key Takeaways

* Private IP addresses are used primarily for communication within private networks such as AWS VPCs.
* Private IP addresses are not directly reachable from the public internet.
* Public IP addresses provide internet-facing connectivity to AWS resources when the required routing and security configuration is in place.
* A VPC should normally use a private RFC 1918 CIDR range for its internal addressing.
* A public IP assigned to an EC2 instance is different from using a public CIDR range for an entire VPC.
* SSH is an application-layer protocol used for secure remote administration.
* SSH normally uses TCP port 22.
* TCP provides the transport mechanism used by SSH.
* Network troubleshooting should distinguish between addressing, routing, and security-control problems.
* Comparing a working resource with a non-working resource is an effective way to identify configuration differences.
* The failed SSH connection to Instance A was the expected result because the connection attempted to use its private IP address from outside the VPC.

