---
title: "Week 7 Worklog"
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

* Learn Amazon Route 53 — AWS’s DNS service
* Build a hybrid DNS system integrating on‑prem DNS with Route 53
* Learn Route 53 Resolver (Outbound/Inbound Endpoints and Rules)
* Learn AWS Command Line Interface (AWS CLI)
* Configure and use AWS CLI
* Practice with Route 53 and AWS CLI

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2   | - Introduction to Amazon Route 53 <br>&emsp; + DNS concepts and Route 53 <br>&emsp; + Route 53 features <br>&emsp; + Domain registration, private hosted zones <br> - Introduction to AWS CLI | 20/10/2025 | 20/10/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Learn Route 53 Resolver <br>&emsp; + Outbound Endpoints — query on‑prem DNS <br>&emsp; + Inbound Endpoints — receive queries from on‑prem <br> - **Practice:** <br>&emsp; + Create VPC and Resolver Endpoints | 21/10/2025 | 21/10/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Learn Resolver Rules <br>&emsp; + Configure DNS forwarding <br>&emsp; + Forward rules to on‑prem DNS <br> - Set up hybrid DNS architecture <br> - **Practice:** <br>&emsp; + Create Resolver Rules | 22/10/2025 | 22/10/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Configure AWS CLI <br>&emsp; + Install AWS CLI <br>&emsp; + `aws configure` credentials <br>&emsp; + Region and Output Format <br>&emsp; + Profiles in AWS CLI <br> - Learn AWS CLI capabilities | 23/10/2025 | 23/10/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - **Integrated practice:** <br>&emsp; + Configure AWS CLI (default profile) <br>&emsp; + Manage Route 53 with CLI (list domains, zones) <br>&emsp; + Manage EC2, RDS, S3 with CLI <br>&emsp; + Write shell scripts with AWS CLI <br>&emsp; + Compare output formats (json, table, yaml, text) | 24/10/2025 | 24/10/2025 | <https://cloudjourney.awsstudygroup.com/> |


### Week 7 Achievements:

* Monday (20/10/2025):
  * Understood Amazon Route 53 — AWS managed DNS
  * Route 53 features:
    * Public domain registration
    * Private Hosted Zones
    * Name resolution
    * Hybrid DNS architecture
  * Understood AWS CLI and its purpose
  * AWS CLI is an open‑source tool to interact with AWS

* Tuesday (21/10/2025):
  * Understood Route 53 Resolver components:
    * Outbound Endpoints — queries from Route 53 to on‑prem DNS
    * Inbound Endpoints — queries from on‑prem to Route 53
    * Resolver Rules — DNS forwarding configuration
  * Understood hybrid DNS architecture
  * Practiced creating VPC and Resolver Endpoints

* Wednesday (22/10/2025):
  * Resolver Rules:
    * Forwarding for specific domains
    * Forward rules to on‑prem DNS servers
    * Conditional forwarding
  * Set up a hybrid DNS architecture
  * Practiced creating Resolver Rules

* Thursday (23/10/2025):
  * Installed AWS CLI (Linux, macOS, Windows)
  * Basic configuration:
    * `aws configure` command
    * Access Key ID
    * Secret Access Key
    * Default Region
    * Output Format
  * Profiles in AWS CLI:
    * Default profile
    * Multiple profiles with `--profile`
    * Stored in config and credentials files
  * AWS CLI capabilities:
    * Access public AWS APIs
    * Manage resources via CLI
    * Automate with shell scripts

* Friday (24/10/2025):
  * Configured AWS CLI (default profile)
  * Managed Route 53 with CLI:
    * `aws route53 list-hosted-zones`
    * `aws route53 list-resource-record-sets`
  * Managed EC2:
    * `aws ec2 describe-instances`
    * `aws ec2 describe-security-groups`
  * Managed RDS:
    * `aws rds describe-db-instances`
  * Managed S3:
    * `aws s3 ls`
    * `aws s3 cp`
  * Wrote shell scripts using AWS CLI
  * Compared output formats: json, table, yaml, text
  * Practiced filtering and processing CLI output
