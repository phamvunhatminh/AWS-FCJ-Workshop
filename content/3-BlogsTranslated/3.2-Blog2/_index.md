---
title: "Blog 2"
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

## **Networking & Content Delivery**

# Dynamic routing using Amazon VPC Route Server

By Ammar Latif and Akshay Choudhry | on September 2, 2025 | in [Post Types](https://aws.amazon.com/blogs/networking-and-content-delivery/category/post-types/), [Architecture](https://aws.amazon.com/blogs/networking-and-content-delivery/category/architecture/), [Industries](https://aws.amazon.com/blogs/networking-and-content-delivery/category/industries/), [Networking & Content Delivery](https://aws.amazon.com/blogs/networking-and-content-delivery/category/networking-content-delivery/), [Technical How‑to](https://aws.amazon.com/blogs/networking-and-content-delivery/category/post-types/technical-how-to/), [Telecommunications](https://aws.amazon.com/blogs/networking-and-content-delivery/category/industries/telecommunications/) | [Permalink](https://aws.amazon.com/blogs/networking-and-content-delivery/dynamic-routing-using-amazon-vpc-route-server/) | [Share](https://aws.amazon.com/blogs/networking-and-content-delivery/dynamic-routing-using-amazon-vpc-route-server/#)

[**Amazon VPC Route Server**](https://docs.aws.amazon.com/vpc/latest/userguide/dynamic-routing-route-server.html) enables dynamic routing in [**Amazon Virtual Private Cloud (Amazon VPC)**](https://aws.amazon.com/vpc/) using Border Gateway Protocol (BGP). You can use Amazon VPC Route Server to intelligently control network traffic between cloud applications and on‑premises systems. Amazon VPC Route Server leverages BGP to provide enhanced control over traffic routes, especially during incidents, while reducing manual intervention and human error.

In this post, we explore various scenarios where application‑level dynamic routing affects traffic delivery to instances and how the system handles failover with minimal disruption.

### Prerequisites

We assume you are familiar with AWS networking concepts related to high availability and failover, such as [**Amazon Elastic Compute Cloud (Amazon EC2)**](https://aws.amazon.com/ec2/), [**Elastic Network Interfaces (ENIs)**](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html), Amazon VPC, VPC routing tables, and [**AWS Availability Zones (AZs)**](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/). We also assume familiarity with basic networking concepts such as IP addressing, CIDR blocks, routing, BGP, and Bidirectional Forwarding Detection (BFD). This post does not focus on defining those services and concepts; instead, it illustrates how they can be used to implement a floating IP solution for application failover. For foundational AWS networking material, refer to AWS documentation on VPC networking and the AWS Networking and Content Delivery blog category. For VPC Route Server concepts, review the [**Getting started guide**](https://docs.aws.amazon.com/vpc/latest/userguide/dynamic-routing-route-server.html).

### Application connectivity scenarios

Traffic inside an Amazon VPC is controlled by route tables. These route tables are associated with subnets, Internet Gateways (IGWs), and Virtual Private Gateways, allowing you to define traffic paths before reaching the destination.
For example, you can define routes in the IGW route table to send traffic through a firewall before reaching the intended target. Similarly, you can route subnet traffic to a NAT Gateway, IGW, peering connections, or a Virtual Private Gateway depending on the use case.

Some applications (such as security and network processing apps) need fine‑grained control of traffic paths to influence how traffic reaches the application before the final destination. These applications typically sit between source and destination to provide network‑related services. A common example is redirecting traffic to a security appliance for inspection before sending it to the actual destination.

While static routes can be used to direct traffic to security appliances or middleboxes, they have significant limitations (unless used with [**Gateway Load Balancer**](https://docs.aws.amazon.com/vpc/latest/userguide/gwlb-route.html) (GWLB)). Static routes require manual intervention during incidents, do not adapt automatically to network changes, and become increasingly complex as the network scales. Manual management increases the risk of human error and lengthens recovery time in the event of disruption.

Dynamic routing solves these challenges by automatically updating route tables, providing better scalability, and enabling failover — all without manual intervention.

Note: AWS recommends using GWLB to ensure high availability and redundancy. Consider this solution only when using EC2 instances with applications that do not support GWLB for inspection.

### Capabilities of VPC Route Server

VPC Route Server enables dynamic routing in a VPC using BGP. Networking applications can use BGP to update VPC route tables, allowing fine‑grained control of traffic inside the VPC and automatic failover between instances deployed within or across AZs. VPC Route Server can automatically update VPC and IGW route tables with preferred routes for IPv4 or IPv6 to achieve routing fault tolerance for workloads. During incidents, the system can automatically reroute VPC traffic, improving manageability and interoperability with third‑party workloads. This capability is especially evident when an AZ fails — the system reroutes traffic to resources in another AZ, and route tables are automatically updated to reflect the new path.

In the following sections, we discuss VPC Route Server routing capabilities in more detail.

### Scenario #1: Using a floating IP for application failover

In this scenario, we demonstrate how a floating IP can achieve seamless failover between two EC2 instances deployed across two AZs in a highly available architecture.
You have a business‑critical application running on an EC2 instance in AZ1, with a standby EC2 instance in AZ2 to ensure high availability. Your application isn’t integrated with GWLB, or GWLB isn’t available (e.g., in a Local Zone).
Your goal is to ensure high availability if the primary instance or its AZ experiences a failure.

You can use an [AWS CloudFormation](https://aws.amazon.com/cloudformation/) template from the [aws‑samples repo](https://aws.amazon.com/cloudformation/) to deploy Scenario #1 in your AWS account. The template creates the following setup:

* A VPC with three subnets across two AZs
* VPC route tables for the three subnets
* An IGW attached to the VPC, with a default route to the IGW in the VPC route table
* A Route Server attached to the VPC — the Route Server uses ASN 65000
* Two VPC Route Server endpoints (RSEs) in each subnet (for high availability)
* Route Server peers
* Two instances to simulate the HA application under test, using [Gobgp](https://github.com/osrg/gobgp)
* Each instance runs BGP with ASN 65001 and peers with RSEs in its subnet
* Gobgp configuration is pre‑set in user‑data and saved in /home/ec2-user/gobgpd.conf
* A test instance to ping the loopback IP of the HA application
* Use [AWS Systems Manager](https://aws.amazon.com/systems-manager/) to access the instances

### Solution overview

We use a floating IP allocated from a non‑VPC CIDR range and used by the application. Clients use this IP to access the application.
When the primary instance fails, traffic to the floating IP is rerouted to the ENI of the standby instance in the second AZ.
This approach minimizes disruption to application availability by combining a floating IP with dynamic VPC routing — without client config changes or manual intervention.

![Figure 1. Instance#1 is active](/images/3-BlogsTranslated/blog2/1.png)

Figure 1. Instance#1 is active

As shown in Figure 1, the application operates in an active/standby model across two AZs.
Both EC2 instances advertise the same loopback IP (e.g., 172.16.1.1/32) via BGP peering with two VPC RSEs placed in the same subnet.
These RSEs are used to ensure redundancy and improve availability of the routing service.

![Figure 2. VPC Route Server endpoints](/images/3-BlogsTranslated/blog2/2.png)Figure 2. VPC Route Server endpoints

![Figure 3. VPC Route Server peers](/images/3-BlogsTranslated/blog2/3.png)Figure 3. VPC Route Server peers

![Figure 4. Route Server RIB table](/images/3-BlogsTranslated/blog2/4.png)Figure 4. Route Server RIB table

To ensure traffic is routed to the active instance, the application uses the BGP AS Path attribute. The active instance advertises a shorter AS Path, while the standby instance prepends AS numbers to make its path less preferred. BGP always chooses the path with the shortest AS Path, ensuring the active instance is selected. Other BGP attributes such as Multi‑Exit Discriminator (MED) can achieve similar prioritization.

1. Both active and standby instances advertise 172.16.1.1/32 via BGP to two RSEs in their respective subnets.  
2. VPC Route Server receives four advertisements for the same prefix. Figure 4 shows loopback 172.16.1.1/32 received by four RSEs.  
3. Per BGP path selection rules, VPC Route Server prefers the active instance’s route due to the shorter AS Path. Figure 4 shows one of the four paths selected and installed.  
4. VPC Route Server identifies the ENI for the active instance and updates the VPC route table to forward 172.16.1.1/32 to ENI‑A.

![Figure 5. VPC route table updated with 172.16.1.1/32 pointing to the active instance ENI](/images/3-BlogsTranslated/blog2/5.png)Figure 5. VPC route table updated with 172.16.1.1/32 pointing to the active instance ENI

Check the Gobgp configuration by connecting to either instance (instance-rs-az1 or instance-rs-az2) via [EC2 Session Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.html).

Gobgp configuration is under /home/ec2-user/gobgpd.conf.

Bash-5.2$ sudo more /home/ec2-user/gobgpd.conf

[global.config]  
as = 65001  
router-id = "10.0.1.203"  
[[neighbors]]  
[neighbors.config]  
neighbor-address = "10.0.1.230"  
peer-as = 65000  
[[neighbors.afi-safis]]  
[neighbors.afi-safis.config]  
afi-safi-name = "ipv4-unicast"  
[[neighbors]]  
[neighbors.config]  
neighbor-address = "10.0.1.136"  
peer-as = 65000  
[[neighbors.afi-safis]]  
[neighbors.afi-safis.config]  
afi-safi-name = "ipv4-unicast"

Use the following command to check BGP neighbor status.  
There will be two neighbors corresponding to the two VPC RSEs in the instance’s subnet.

sh-5.2$ sudo /home/ec2-user/gobgp neighbor  
Peer AS Up/Down State |#Received Accepted  
10.0.1.136 65000 22:43:07 Establ | 0 0  
10.0.1.230 65000 22:43:08 Establ | 0 0

Check whether the loopback route is being advertised via BGP.

sh-5.2$ sudo /home/ec2-user/gobgp global rib  
Network Next Hop AS_PATH Age Attrs  
*> 172.16.1.1/32 0.0.0.0 22:42:21 [{Origin: ?}]

To validate the routing setup, access the “test‑instance” via Systems Manager.  
Once logged in, ping 172.16.1.1 and you’ll get responses from the active instance “instance-rs-az1”.

sh-5.2$ ping 172.16.1.1  
PING 172.16.1.1 (172.16.1.1) 56(84) bytes of data.  
64 bytes from 172.16.1.1: icmp_seq=1 ttl=127 time=0.712 ms  
64 bytes from 172.16.1.1: icmp_seq=2 ttl=127 time=0.338 ms  
64 bytes from 172.16.1.1: icmp_seq=3 ttl=127 time=0.378 ms

**Failure detection and recovery**

To simulate failover, shut down the active instance (instance-rs-az1).

1. If the active instance fails or loses connectivity, BGP detects the fault based on the configured timeout.  
2. VPC Route Server marks the BGP session with the active instance as down and withdraws the route from the RIB table.  
3. BGP re‑convergence is triggered, and the standby instance’s advertised route is selected as the best path.  
4. The VPC route table is updated to forward traffic for 172.16.1.1/32 to the standby instance’s ENI (ENI‑B).  
5. Traffic seamlessly shifts to the standby instance, maintaining application availability without user disruption.

To validate routing, access the “test‑instance” via Systems Manager.  
Ping 172.16.1.1 and responses will come from the now‑active “instance-rs-az2”.

sh-5.2$ ping 172.16.1.1  
PING 172.16.1.1 (172.16.1.1) 56(84) bytes of data.  
64 bytes from 172.16.1.1: icmp_seq=1 ttl=127 time=0.712 ms  
64 bytes from 172.16.1.1: icmp_seq=2 ttl=127 time=0.338 ms  
64 bytes from 172.16.1.1: icmp_seq=3 ttl=127 time=0.378 ms

For fast failure detection, enable Bidirectional Forwarding Detection (BFD) between the application and the RSEs.
BFD significantly reduces the time required to detect link or application failures.

![Figure 6. Instance2 took over as active](/images/3-BlogsTranslated/blog2/6.png)Figure 6. Instance #2 took over as active

![Figure 7. Route table updated to point to Inst2 ENI](/images/3-BlogsTranslated/blog2/7.png)Figure 7. Route table updated to point to Instance #2 ENI

This scenario demonstrates a robust approach to implementing floating IP‑based failover in AWS using standard routing protocols like BGP and BFD.
It enables fast, reliable, transparent failover across AZs without DNS updates or manual intervention — ideal for workloads requiring high availability, minimal downtime, and maximum resiliency.

### Scenario #2: Inspecting VPC ingress traffic

Consider a centralized security model where firewall appliances — deployed as EC2 instances — inspect all north‑south or east‑west VPC traffic.
These firewalls are critical to your security posture and must always be available to inspect and forward traffic.
To maintain high availability, deploy two firewall EC2 instances across two AZs.
Your goal is to ensure that if the active firewall fails, traffic is seamlessly redirected to the standby firewall.

In this scenario, we show how to implement HA and failover for stateful firewalls deployed across multiple AZs in AWS using VPC Route Server and dynamic route updates.

### Solution overview

All traffic entering the VPC via the IGW is first routed to the firewall for inspection before being forwarded to the application subnet.
Similarly, all traffic leaving the application subnet passes through the firewall before exiting to the Internet.

The diagram below shows a firewall installed on an EC2 instance in subnet A.
It inspects traffic from IGW to subnet B (application subnet) and from subnet B back to IGW.

![](/images/3-BlogsTranslated/blog2/8.png)Figure 8. Scenario #2 — Firewall #1 is active

Each firewall establishes four BGP sessions: two for subnet A and two for subnet B, including the application subnet and IGW route tables.

To ensure only one firewall is used at a time, BGP path preference is tuned via metrics.
We focus on the following metrics:

* **AS_Path:** Shows the sequence of Autonomous System numbers a route traverses. It prevents loops and serves as a selection criterion — shorter AS_Path is preferred.
* **MED (Multi‑Exit Discriminator):** Influences inbound traffic by suggesting the preferred entry point when multiple connections exist between autonomous systems. Lower MED is preferred.

The active firewall advertises prefixes with higher‑priority BGP attributes, while the standby firewall advertises the same prefixes with lower‑priority attributes.
In this scenario, we use AS Path Prepending — the standby firewall prepends more AS numbers when advertising to RSEs, making its path less preferred.

### Internet Gateway route table

IGW‑associated route tables control inbound Internet traffic paths inside the VPC.
Customers commonly use this table to insert firewalls or other virtual network functions into inbound Internet paths.

Both active and standby firewalls peer with VPC Route Server and advertise the application subnet CIDR to the RSEs.
However, the standby firewall advertises with a longer AS Path.
VPC Route Server runs BGP Best Path Selection and installs the route advertised by the active firewall.

The IGW route table contains:

Application subnet CIDR —> Active Firewall ENI.

VPC routes inbound traffic destined for the application subnet to the active firewall’s ENI.

### Application subnet route table

Both firewalls peer with VPC Route Server and advertise [0.0.0.0/0](http://0.0.0.0/0) to the RSEs.
The standby firewall advertises [0.0.0.0/0](http://0.0.0.0/0) with a longer AS Path, making it less preferred.
VPC Route Server selects the active firewall’s route and installs it.

The application subnet route table contains:

0.0.0.0/0 —> Active Firewall ENI.

This routes traffic from application servers to the active firewall before exiting to the Internet.

### Firewall subnet route table

The provider subnet (where the firewall is deployed) route table includes static routes such as:

0.0.0.0/0 —> igw-id

This routes all traffic to the IGW.

### Failover detection with BFD

BFD is enabled on each BGP session between the firewalls and the VPC RSEs.
BFD enables sub‑second failure detection by continuously exchanging control packets.

When a firewall fails:

1. BFD detects the failure of the BGP session between the active firewall and the RSEs.
2. RSEs mark the BGP session as DOWN.
3. RSEs withdraw the preferred routes — internal and external prefixes — previously advertised by the failed firewall.
4. BGP re‑convergence is triggered — RSEs select the standby firewall’s advertised routes.
5. The new route becomes active in the VPC routing control plane.
6. Traffic is automatically redirected to the standby firewall.

![](/images/3-BlogsTranslated/blog2/9.png)Figure 9. Firewall #1 failure causes traffic to be rerouted to Firewall #2

### Recovery / Failback

When the failed firewall is restored and re‑establishes BGP and BFD sessions:

1. It resumes advertising preferred BGP attributes.
2. RSEs detect the higher‑priority route and shift traffic back to the restored firewall.

This can be automated or governed by admin policy — e.g., preemptive vs. non‑preemptive failover.

### Benefits of VPC Route Server‑based failover with BGP + BFD

1. **Fast convergence:** Sub‑second failure detection via BFD.
2. **Fully automated:** No scripts or manual intervention.
3. **Scalable:** Works with many prefixes and instances.
4. **Cloud‑native control:** Integrates directly with VPC routing.
5. **Protocol standardization:** Uses industry‑standard BGP behavior.

### Considerations

1. Routing re‑convergence may cause brief downtime.  
  → Prefer GWLB for application failover if supported by your application.
2. Disable route propagation when managing routes manually.
3. Use BFD or other fast detection mechanisms for faster convergence.
4. Ensure symmetric routing if performing return‑path inspection.
5. Enable monitoring and alerting for system health, route changes, and failover events.

### Conclusion

In this post, we explored how to use Amazon VPC Route Server to build scalable, fault‑tolerant, and secure cloud networking by enabling failover for critical applications and designing high‑availability architectures.

We covered two different architectural models with practical implementation details.
VPC Route Server unlocks advanced routing in AWS by integrating industry‑standard protocols like BGP and BFD into native VPC networking.

To get started today, see the [documentation](https://docs.aws.amazon.com/vpc/latest/userguide/dynamic-routing-route-server.html) and the [Amazon VPC Route Server Get started tutorial](https://docs.aws.amazon.com/vpc/latest/userguide/route-server-tutorial.html).

***Update (September 15, 2025):*** A previous version of this post used diagrams with older AWS icons. The post has been updated to reflect the current AWS Architecture Icons.

**About the authors**

**Ammar Latif**
![image](/images/3-BlogsTranslated/blog2/10.jpg)
Ammar is a Principal Solutions Architect in AWS Worldwide Telecom Business Unit. He enjoys helping customers use cloud technologies to address business challenges. Throughout his career, Ammar has worked with many Telecom and Media customers globally. He holds a Ph.D. from New Jersey Institute of Technology.

### Akshay Choudhry
![image](/images/3-BlogsTranslated/blog2/11.jpg)
Akshay is a Principal Product Manager in the Networking and Security Services Team at Amazon Web Services. He focuses on making Amazon Virtual Private Cloud (VPC) intuitive and secure for millions of customers running their workloads on AWS. In his free time, he enjoys exploring nature, trying new restaurants, and spending time with friends and family.

TAGS: [Amazon VPC](https://aws.amazon.com/blogs/networking-and-content-delivery/tag/amazon-vpc/), [AWS CloudFormation](https://aws.amazon.com/blogs/networking-and-content-delivery/tag/aws-cloudformation/), [BGP](https://aws.amazon.com/blogs/networking-and-content-delivery/tag/bgp/)

