---
title: "Week 11 Worklog"
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

* Study and discuss the deployment architecture on AWS
* Learn the 13 core AWS services used in the project
* Understand the roles and integrations between services
* Create a detailed deployment plan
* Estimate cost and optimize the architecture

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                 | Start Date | Completion Date | Reference Material                        |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ----------------------------------------- |
| 2   | - Discuss deployment architecture <br>&emsp; + Sketch API Gateway, Lambda, RDS <br>&emsp; + Sketch CloudFront, S3 for FE <br>&emsp; + Sketch authentication with Cognito <br> - Overview by layers     | 17/11/2025 | 17/11/2025      |
| 3   | - Learn API Gateway and Lambda <br>&emsp; + Create REST API endpoints <br>&emsp; + Serverless compute with Lambda <br>&emsp; + IAM permissions <br> - **Practice:** <br>&emsp; + Create an API endpoint with Lambda | 18/11/2025 | 18/11/2025      |
| 4   | - Learn Cognito, SQS, Step Functions <br>&emsp; + User authentication and authorization <br>&emsp; + Message queue for async tasks <br>&emsp; + Workflow orchestration <br> - **Practice:** <br>&emsp; + Set up a Cognito user pool | 19/11/2025 | 19/11/2025      |
| 5   | - Learn Bedrock, SES, WAF <br>&emsp; + AI responses and recommendations <br>&emsp; + Email notifications <br>&emsp; + API protection <br> - Learn RDS MySQL, Route 53, CloudWatch <br> - Learn CloudFront, S3 | 20/11/2025 | 20/11/2025      |
| 6   | - **Integrated practice:** <br>&emsp; + Redraw the end-to-end architecture (13 services) <br>&emsp; + Draft a detailed deployment plan <br>&emsp; + Estimate cost <br>&emsp; + Assess Well-Architected Framework compliance | 21/11/2025 | 21/11/2025      |


### Week 11 Achievements:

* Monday: Architecture discussion — Frontend (S3 + CloudFront + Route 53), Backend (API Gateway + Lambda + RDS), Auth (Cognito), AI (Bedrock), Messaging (SQS, SES), Workflow (Step Functions), Monitoring (CloudWatch, WAF)
* Tuesday: Studied API Gateway, Lambda, and IAM; created a REST API endpoint with Lambda
* Wednesday: Studied Cognito, SQS, Step Functions; set up a Cognito user pool
* Thursday: Studied Bedrock, SES, WAF, RDS, Route 53, CloudWatch, CloudFront, S3
* Friday: Finalized the 13-service architecture, deployment plan, cost estimate, and WAF compliance assessment
