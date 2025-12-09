---
title: "Week 8 Worklog"
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* Learn Amazon DynamoDB — fully managed NoSQL database
* Practice programming with DynamoDB using Python
* Learn Amazon ElastiCache — in‑memory caching service
* Practice Redis on ElastiCache
* Learn Amazon CloudFront — Content Delivery Network (CDN)
* Practice hosting static content on S3 with CloudFront acceleration
* Align architecture with the AWS Well‑Architected Framework

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2   | - Learn Amazon DynamoDB (NoSQL) <br>&emsp; + Tables, Items, Attributes <br>&emsp; + Primary Key (Partition & Sort Key) <br>&emsp; + Read/Write Capacity Units <br>&emsp; + Billing Model <br> - Learn Python boto3 SDK | 27/10/2025 | 27/10/2025 |
| 3   | - **DynamoDB with Python (Practice):** <br>&emsp; + Install boto3 <br>&emsp; + Create a DynamoDB table <br>&emsp; + Put Item <br>&emsp; + Get Item <br>&emsp; + Query and Scan <br>&emsp; + Update/Delete Item | 28/10/2025 | 28/10/2025 |
| 4   | - Learn Amazon ElastiCache <br>&emsp; + Redis cache engine <br>&emsp; + Node types and cluster configuration <br>&emsp; + TTL (Time To Live) <br>&emsp; + Cache invalidation <br> - Caching use cases | 29/10/2025 | 29/10/2025 |
| 5   | - **ElastiCache‑Redis Practice:** <br>&emsp; + Create an ElastiCache cluster (Redis) <br>&emsp; + Connect to Redis endpoint <br>&emsp; + Set/Get key‑value <br>&emsp; + Expire commands <br>&emsp; + Monitor performance <br> - Learn Redis data structures | 30/10/2025 | 30/10/2025 |
| 6   | - Learn Amazon CloudFront (CDN) <br>&emsp; + Origins (S3, Custom, ELB) <br>&emsp; + Distributions <br>&emsp; + Edge locations <br>&emsp; + Cache behaviors <br> - **Practice:** <br>&emsp; + Create S3 bucket and upload index.html <br>&emsp; + Create CloudFront Distribution <br>&emsp; + Configure IAM permissions <br>&emsp; + Test caching and acceleration | 31/10/2025 | 31/10/2025 |


### Week 8 Achievements:

* Monday (27/10/2025):
  * Understood Amazon DynamoDB as a fully managed NoSQL database
  * DynamoDB concepts:
    * Tables, Items, Attributes
    * Primary Key: Partition Key (required) and Sort Key (optional)
  * Billing model:
    * Read Capacity Units (RCU)
    * Write Capacity Units (WCU)
    * On‑Demand vs Provisioned modes
  * Understood Python boto3 SDK for DynamoDB

* Tuesday (28/10/2025):
  * Installed boto3: `pip install boto3`
  * Practiced creating a DynamoDB table (keys, capacity)
  * Practiced Put Item, Get Item, Query, Scan, Update, Delete

* Wednesday (29/10/2025):
  * Understood Amazon ElastiCache (managed in‑memory caching)
  * Redis engine basics and data types
  * Node types and cluster configuration
  * TTL and cache invalidation
  * Caching use cases: session storage, leaderboards, counters, hot data

* Thursday (30/10/2025):
  * Created an ElastiCache (Redis) cluster
  * Connected via `redis-py`
  * Practiced Set/Get, Exists, Expire/TTL
  * Monitored performance; reviewed eviction policies and hit/miss ratio
  * Reviewed Redis structures: Lists, Sets, Sorted Sets, Hashes

* Friday (31/10/2025):
  * Understood Amazon CloudFront (CDN):
    * Accelerates static and dynamic content via edge locations
  * Origins: S3, Custom (EC2/ELB), MediaStore
  * Distributions: Web and RTMP
  * Edge locations and caching close to users
  * Cache behaviors: path patterns, TTLs, allowed methods, compression
  * Practiced S3 static website hosting and CloudFront OAI
  * Tested caching (X‑Cache), monitored via CloudWatch, compared S3 vs CloudFront
  * Well‑Architected considerations: Reliability, Performance, Cost, Security
