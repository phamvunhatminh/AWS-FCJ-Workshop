---
title: "Week 6 Worklog"
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

* Deploy applications using Auto Scaling Groups (ASG)
* Learn Elastic Load Balancer (ELB) and load balancing
* Create Launch Templates for ASG
* Learn Amazon CloudWatch for monitoring and management
* Learn CloudWatch Container Insights
* Practice an end-to-end scaling and load-balancing solution

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2   | - Introduction to Auto Scaling Groups (ASG) <br>&emsp; + ASG benefits <br>&emsp; + High availability and elastic scaling <br>&emsp; + Cost optimization <br> - Introduction to Elastic Load Balancer | 13/10/2025 | 13/10/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Learn Launch Templates <br>&emsp; + Create from an EC2 instance <br>&emsp; + Configure Launch Templates <br> - **Practice:** <br>&emsp; + Create Launch Template <br>&emsp; + Configure Security Groups | 14/10/2025 | 14/10/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Set up Elastic Load Balancer <br>&emsp; + Load Balancer types <br>&emsp; + Health Checks <br>&emsp; + Target Groups <br> - **Practice:** <br>&emsp; + Create ELB and Target Groups | 15/10/2025 | 15/10/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Create Auto Scaling Group <br>&emsp; + Configure policies (scale up/down) <br>&emsp; + Set CloudWatch metrics <br>&emsp; + Attach ASG to Load Balancer <br> - Learn Amazon CloudWatch | 16/10/2025 | 16/10/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - **Integrated practice:** <br>&emsp; + Create Launch Template <br>&emsp; + Create ELB <br>&emsp; + Create ASG <br>&emsp; + Test scaling (increase/decrease load) <br>&emsp; + Monitor CloudWatch metrics | 17/10/2025 | 17/10/2025 | <https://cloudjourney.awsstudygroup.com/> |


### Week 6 Achievements:

* Monday (13/10/2025):
  * Understood Auto Scaling Groups (ASG) and benefits:
    * High availability — automatic replacement of unhealthy instances
    * Elastic scalability — scale in/out based on demand
    * Effective load distribution with Elastic Load Balancer
    * Cost optimization — only the resources you need
    * High automation
  * Understood ELB and its role in the system

* Tuesday (14/10/2025):
  * Launch Templates:
    * Purpose and concepts
    * Create from an existing EC2 instance
    * Configure AMI, Instance Type, Key Pair, Security Groups
  * Practiced creating a Launch Template
  * Configured Security Groups for the Launch Template

* Wednesday (15/10/2025):
  * Elastic Load Balancer:
    * Types (ALB, NLB, CLB)
    * Health Checks
    * Target Groups
    * Routing rules
  * Created an ELB
  * Configured Target Groups
  * Verified load balancer functionality

* Thursday (16/10/2025):
  * Created an Auto Scaling Group:
    * Set min/max/desired capacity
    * Configure scaling policies (up/down)
    * Configure metrics via CloudWatch (CPU, RAM, Network)
    * Attach ASG to Load Balancer
  * Understood Amazon CloudWatch:
    * Monitoring and management service
    * Metrics and Logs
    * 15-month data retention
    * Metric math
  * Learned CloudWatch Container Insights

* Friday (17/10/2025):
  * End-to-end practice:
    * Create Launch Template from FCJ Management app
    * Create ELB with Health Checks
    * Create Auto Scaling Group
    * Load test to trigger scale out
    * Reduce load to trigger scale in
    * Monitor CloudWatch metrics (CPU, Network, request count)
    * Verify load distribution across instances
    * Clean up resources (ASG, ELB, Launch Template)
