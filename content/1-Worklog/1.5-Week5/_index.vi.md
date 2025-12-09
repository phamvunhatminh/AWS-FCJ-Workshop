---
title: "Worklog Tuần 5"
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Tìm hiểu Amazon Relational Database Service (Amazon RDS)
* Hiểu các lợi ích chính của RDS - dịch vụ quản lý cơ sở dữ liệu
* Học các hệ thống cơ sở dữ liệu được hỗ trợ trên RDS
* Tìm hiểu tính năng quản lý, bảo mật, mã hóa của RDS
* Hiểu Multi-AZ, Read Replicas, DB Snapshots và các chiến lược phục hồi
* Thực hành tạo và quản lý RDS instances

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Giới thiệu Amazon RDS <br>&emsp; + Khái niệm RDS và lợi ích chính <br>&emsp; + Các hệ thống cơ sở dữ liệu được hỗ trợ <br>&emsp; + Khi nào nên sử dụng RDS vs các dịch vụ khác                                            | 06/10/2025   | 06/10/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Tìm hiểu tính năng quản lý RDS <br>&emsp; + Sao lưu tự động và vá lỗi <br>&emsp; + Mở rộng dễ dàng <br>&emsp; + DB Subnet Groups <br> - **Thực hành:** <br>&emsp; + Tạo VPC và DB Subnet Group | 07/10/2025   | 07/10/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Tìm hiểu bảo mật và mã hóa RDS <br>&emsp; + Mã hóa khi nghỉ (Encryption at rest) <br>&emsp; + Mã hóa SSL/TLS trong quá trình truyền tải <br>&emsp; + AWS KMS integration <br> - **Thực hành:** <br>&emsp; + Tạo RDS instance với mã hóa | 08/10/2025   | 08/10/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Tìm hiểu Multi-AZ, Read Replicas và DR: <br>&emsp; + Multi-AZ deployments cho high availability <br>&emsp; + Read Replicas cho scaling đọc <br>&emsp; + DB Snapshots và khôi phục <br> - Chiến lược phục hồi thảm họa                  | 09/10/2025   | 10/10/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - **Thực hành tổng hợp:** <br>&emsp; + Tạo RDS instance (MySQL/PostgreSQL) <br>&emsp; + Cấu hình Multi-AZ <br>&emsp; + Tạo Read Replicas <br>&emsp; + Tạo DB Snapshots và kiểm tra khôi phục                                                                                         | 10/10/2025   | 10/10/2025      | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 5:

* **Thứ 2 (06/10/2025):**
  * Hiểu Amazon RDS là dịch vụ quản lý cho cơ sở dữ liệu quan hệ
  * Nắm rõ các lợi ích chính của RDS:
    * Thay thế dễ dàng cho các instance DB truyền thống
    * Sao lưu tự động và vá lỗi
    * Mở rộng dễ dàng
  * Biết các hệ thống DB được hỗ trợ: Aurora, MySQL, MariaDB, Oracle, SQL Server, PostgreSQL
  * Hiểu khi nào sử dụng RDS vs EC2, DynamoDB, RedShift, Neptune, ElastiCache

* **Thứ 3 (07/10/2025):**
  * Hiểu các tính năng quản lý của RDS:
    * Bảo mật và vá lỗi tự động
    * Sao lưu tự động
    * Cập nhật phần mềm DB engine
    * Mở rộng lưu trữ và tính toán
  * Tìm hiểu DB Subnet Groups và cách hoạt động
  * Thực hành tạo VPC và DB Subnet Group

* **Thứ 4 (08/10/2025):**
  * Hiểu mã hóa trong RDS:
    * Mã hóa khi nghỉ (Encryption at rest) sử dụng AWS KMS
    * Mã hóa SSL/TLS trong quá trình truyền tải
    * Mã hóa tất cả snapshots, backups, read replicas
  * Biết rằng không thể mã hóa DB hiện có (phải tạo mới từ snapshot)
  * Thực hành tạo RDS instance với mã hóa

* **Thứ 5 (09-10/10/2025):**
  * Hiểu Multi-AZ deployments:
    * Sao chép đồng bộ cho high availability
    * Failover tự động
    * Bảo vệ trước lỗi AZ
  * Hiểu Read Replicas:
    * Sao chép không đồng bộ
    * Mở rộng khả năng đọc
    * Có thể Cross-AZ hoặc Cross-Region
    * Tối đa 5 read replicas của một DB
  * Tìm hiểu DB Snapshots và khôi phục
  * Hiểu chiến lược phục hồi thảm họa (DR)

* **Thứ 6 (10/10/2025):**
  * Thực hành tạo RDS instance (MySQL hoặc PostgreSQL)
  * Cấu hình Multi-AZ deployment cho high availability
  * Tạo Read Replicas cho mở rộng đọc
  * Tạo và quản lý DB Snapshots
  * Kiểm tra quá trình khôi phục từ snapshot
  * Hiểu monitoring, maintenance windows, và billing của RDS


