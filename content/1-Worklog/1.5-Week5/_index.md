---
title: "Week 5 Worklog"
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* Learn Amazon Relational Database Service (Amazon RDS)
* Understand the key benefits of a managed database service
* Learn the database engines supported by RDS
* Learn RDS management, security, and encryption features
* Understand Multi-AZ, Read Replicas, DB Snapshots, and recovery strategies
* Practice creating and managing RDS instances

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2   | - Introduction to Amazon RDS <br>&emsp; + What RDS is and key benefits <br>&emsp; + Supported DB engines <br>&emsp; + When to use RDS vs other services | 06/10/2025 | 06/10/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Learn RDS management features <br>&emsp; + Automated backups and patching <br>&emsp; + Easy scaling <br>&emsp; + DB Subnet Groups <br> - **Practice:** <br>&emsp; + Create VPC and DB Subnet Group | 07/10/2025 | 07/10/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Learn RDS security and encryption <br>&emsp; + Encryption at rest <br>&emsp; + SSL/TLS encryption in transit <br>&emsp; + AWS KMS integration <br> - **Practice:** <br>&emsp; + Create an encrypted RDS instance | 08/10/2025 | 08/10/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Learn Multi-AZ, Read Replicas, and DR: <br>&emsp; + Multi-AZ for high availability <br>&emsp; + Read Replicas for read scaling <br>&emsp; + DB Snapshots and restore <br> - Disaster recovery strategies | 09/10/2025 | 10/10/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - **Integrated practice:** <br>&emsp; + Create an RDS instance (MySQL/PostgreSQL) <br>&emsp; + Configure Multi-AZ <br>&emsp; + Create Read Replicas <br>&emsp; + Create DB Snapshots and test restore | 10/10/2025 | 10/10/2025 | <https://cloudjourney.awsstudygroup.com/> |


### Week 5 Achievements:

* Monday (06/10/2025):
  * Understood Amazon RDS as a managed relational database service
  * Key benefits of RDS:
    * Easy replacement for self-managed DB instances
    * Automated backups and patching
    * Easy scaling
  * Supported engines: Aurora, MySQL, MariaDB, Oracle, SQL Server, PostgreSQL
  * When to use RDS vs EC2, DynamoDB, Redshift, Neptune, ElastiCache

* Tuesday (07/10/2025):
  * RDS management features:
    * Security and automatic patching
    * Automated backups
    * DB engine software updates
    * Storage and compute scaling
  * Learned DB Subnet Groups
  * Practiced creating a VPC and DB Subnet Group

* Wednesday (08/10/2025):
  * Encryption in RDS:
    * Encryption at rest using AWS KMS
    * SSL/TLS encryption in transit
    * Encryption for snapshots, backups, and read replicas
  * Noted: existing DBs cannot be encrypted directly (must recreate from snapshot)
  * Practiced creating an encrypted RDS instance

* Thursday (09-10/10/2025):
  * Multi-AZ deployments:
    * Synchronous replication for high availability
    * Automatic failover
    * AZ failure protection
  * Read Replicas:
    * Asynchronous replication
    * Read scaling
    * Cross-AZ or Cross-Region options
    * Up to 5 read replicas per DB
  * DB Snapshots and restore
  * Disaster Recovery (DR) strategy

* Friday (10/10/2025):
  * Created an RDS instance (MySQL or PostgreSQL)
  * Configured Multi-AZ for high availability
  * Created Read Replicas for read scaling
  * Created and managed DB Snapshots
  * Tested restore from snapshot
  * Understood RDS monitoring, maintenance windows, and billing
