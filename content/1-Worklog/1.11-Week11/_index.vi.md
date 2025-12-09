---
title: "Worklog Tuần 11"
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

* Thảo luận kiến trúc deploy dự án trên AWS
* Tìm hiểu 13 dịch vụ AWS chính được sử dụng trong dự án
* Hiểu vai trò và tích hợp giữa các dịch vụ
* Lập kế hoạch deployment chi tiết
* Đánh giá chi phí và tối ưu hóa kiến trúc

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Thảo luận kiến trúc deployment <br>&emsp; + Phác họa API Gateway, Lambda, RDS <br>&emsp; + Phác họa CloudFront, S3 cho FE <br>&emsp; + Phác họa xác thực với Cognito <br> - Tổng quan kiến trúc theo từng layer | 17/11/2025   | 17/11/2025      |
| 3   | - Tìm hiểu API Gateway và Lambda <br>&emsp; + Tạo REST API endpoints <br>&emsp; + Serverless compute với Lambda <br>&emsp; + IAM permissions <br> - **Thực hành:** <br>&emsp; + Tạo một endpoint API với Lambda | 18/11/2025   | 18/11/2025      |
| 4   | - Tìm hiểu Cognito, SQS, Step Functions <br>&emsp; + User authentication và authorization <br>&emsp; + Message queue cho async tasks <br>&emsp; + Workflow orchestration <br> - **Thực hành:** <br>&emsp; + Setup Cognito user pool | 19/11/2025   | 19/11/2025      |
| 5   | - Tìm hiểu Bedrock, SES, WAF <br>&emsp; + AI responses và recommendations <br>&emsp; + Email notifications <br>&emsp; + API protection <br> - Tìm hiểu RDS MySQL, Route 53, CloudWatch <br> - Tìm hiểu CloudFront, S3 | 20/11/2025   | 20/11/2025      |
| 6   | - **Thực hành tổng hợp:** <br>&emsp; + Vẽ lại kiến trúc đầy đủ (13 services) <br>&emsp; + Lập kế hoạch deployment chi tiết <br>&emsp; + Tính toán cost estimate <br>&emsp; + Đánh giá Well-Architected Framework compliance | 21/11/2025   | 21/11/2025      |


### Kết quả đạt được tuần 11:

* **Thứ 2:** Thảo luận kiến trúc: Frontend (S3 + CloudFront + Route 53), Backend (API Gateway + Lambda + RDS), Auth (Cognito), AI (Bedrock), Messaging (SQS, SES), Workflow (Step Functions), Monitoring (CloudWatch, WAF)
* **Thứ 3:** Tìm hiểu API Gateway, Lambda, IAM permissions; Tạo REST API endpoint với Lambda
* **Thứ 4:** Tìm hiểu Cognito, SQS, Step Functions; Setup Cognito user pool
* **Thứ 5:** Tìm hiểu Bedrock, SES, WAF, RDS, Route 53, CloudWatch, CloudFront, S3
* **Thứ 6:** Vẽ kiến trúc đầy đủ (13 services), lập kế hoạch deployment, tính cost estimate, đánh giá Well-Architected Framework
