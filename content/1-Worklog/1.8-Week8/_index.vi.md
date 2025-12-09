---
title: "Worklog Tuần 8"
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Tìm hiểu Amazon DynamoDB - dịch vụ cơ sở dữ liệu NoSQL được quản lý hoàn toàn
* Thực hành lập trình với Amazon DynamoDB sử dụng Python
* Tìm hiểu Amazon ElastiCache - dịch vụ caching in-memory
* Thực hành Redis trên ElastiCache
* Tìm hiểu Amazon CloudFront - dịch vụ phân phối nội dung (CDN)
* Thực hành lưu trữ nội dung tĩnh trên S3 với CloudFront acceleration
* Đảm bảo kiến trúc phù hợp với AWS Well-Architected Framework

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu Amazon DynamoDB (NoSQL database) <br>&emsp; + Khái niệm Tables, Items, Attributes <br>&emsp; + Primary Key (Partition & Sort Key) <br>&emsp; + Read/Write Capacity Units <br>&emsp; + Billing Model <br> - Tìm hiểu Python SDK boto3 cho DynamoDB | 27/10/2025   | 27/10/2025      |
| 3   | - **Thực hành DynamoDB với Python:** <br>&emsp; + Cài đặt boto3 library <br>&emsp; + Tạo DynamoDB table <br>&emsp; + Put Item (ghi dữ liệu) <br>&emsp; + Get Item (đọc dữ liệu) <br>&emsp; + Query và Scan operations <br>&emsp; + Update/Delete Item | 28/10/2025   | 28/10/2025      |
| 4   | - Tìm hiểu Amazon ElastiCache <br>&emsp; + Redis cache engine <br>&emsp; + Node types và Cluster configuration <br>&emsp; + TTL (Time To Live) <br>&emsp; + Cache invalidation <br> - Tìm hiểu use cases của caching | 29/10/2025   | 29/10/2025      |
| 5   | - **Thực hành ElastiCache-Redis:** <br>&emsp; + Tạo ElastiCache cluster (Redis) <br>&emsp; + Kết nối tới Redis endpoint <br>&emsp; + Set/Get key-value <br>&emsp; + Expire commands <br>&emsp; + Monitor performance <br> - Tìm hiểu Redis data structures | 30/10/2025   | 30/10/2025      |
| 6   | - Tìm hiểu Amazon CloudFront (CDN) <br>&emsp; + Origins (S3, Custom, ELB) <br>&emsp; + Distributions <br>&emsp; + Edge locations <br>&emsp; + Cache behaviors <br> - **Thực hành:** <br>&emsp; + Tạo S3 bucket và upload index.html <br>&emsp; + Tạo CloudFront Distribution <br>&emsp; + Cấu hình IAM permissions <br>&emsp; + Test caching và acceleration | 31/10/2025   | 31/10/2025      |


### Kết quả đạt được tuần 8:

* Thứ 2 (27/10/2025):
	* Hiểu Amazon DynamoDB là NoSQL được quản lý hoàn toàn
	* Khái niệm DynamoDB: Tables, Items, Attributes; Primary Key gồm Partition Key (bắt buộc) và Sort Key (tùy chọn)
	* Mô hình tính phí: RCU, WCU; chế độ On‑Demand vs Provisioned
	* Nắm Python boto3 SDK cho DynamoDB

* Thứ 3 (28/10/2025):
	* Cài đặt boto3: `pip install boto3`
	* Thực hành tạo bảng (khóa, capacity)
	* Thực hành Put, Get, Query, Scan, Update, Delete

* Thứ 4 (29/10/2025):
	* Hiểu Amazon ElastiCache (caching in‑memory được quản lý)
	* Redis cơ bản và data types
	* Node types và cấu hình cluster
	* TTL và cache invalidation
	* Use case: session storage, leaderboards, counters, hot data

* Thứ 5 (30/10/2025):
	* Tạo ElastiCache (Redis) cluster
	* Kết nối với `redis-py`
	* Thực hành Set/Get, Exists, Expire/TTL
	* Theo dõi hiệu năng; ôn eviction policies và hit/miss ratio
	* Ôn cấu trúc Redis: Lists, Sets, Sorted Sets, Hashes

* Thứ 6 (31/10/2025):
	* Hiểu Amazon CloudFront (CDN): tăng tốc qua edge locations
	* Origins: S3, Custom (EC2/ELB), MediaStore
	* Distributions: Web và RTMP
	* Edge locations và caching gần người dùng
	* Cache behaviors: path patterns, TTLs, allowed methods, compression
	* Thực hành S3 static website và CloudFront OAI
	* Kiểm tra caching (X‑Cache), theo dõi CloudWatch, so sánh S3 vs CloudFront
	* Well‑Architected: Reliability, Performance, Cost, Security


