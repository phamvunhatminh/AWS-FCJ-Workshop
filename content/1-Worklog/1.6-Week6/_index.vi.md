---
title: "Worklog Tuần 6"
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

* Triển khai ứng dụng sử dụng Auto Scaling Group (ASG)
* Tìm hiểu Elastic Load Balancer (ELB) và cân bằng tải
* Khởi tạo Launch Template cho ASG
* Tìm hiểu Amazon CloudWatch - dịch vụ theo dõi và quản lý
* Tìm hiểu CloudWatch Container Insights
* Thực hành triển khai toàn bộ giải pháp scaling và load balancing

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Giới thiệu Auto Scaling Group (ASG) <br>&emsp; + Lợi ích của ASG <br>&emsp; + Tính sẵn sàng cao và mở rộng linh hoạt <br>&emsp; + Tiết kiệm chi phí <br> - Giới thiệu Elastic Load Balancer                                            | 13/10/2025   | 13/10/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Tìm hiểu Launch Template <br>&emsp; + Tạo Launch Template từ EC2 instance <br>&emsp; + Cấu hình Launch Template <br> - **Thực hành:** <br>&emsp; + Khởi tạo Launch Template <br>&emsp; + Cấu hình Security Groups | 14/10/2025   | 14/10/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Thiết lập Elastic Load Balancer <br>&emsp; + Giới thiệu Load Balancer types <br>&emsp; + Cấu hình Health Checks <br>&emsp; + Cấu hình Target Groups <br> - **Thực hành:** <br>&emsp; + Tạo ELB và Target Groups | 15/10/2025   | 15/10/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Khởi tạo Auto Scaling Group <br>&emsp; + Cấu hình ASG policies (scale up/down) <br>&emsp; + Thiết lập metrics dựa trên CloudWatch <br>&emsp; + Kết nối ASG với Load Balancer <br> - Tìm hiểu Amazon CloudWatch                  | 16/10/2025   | 16/10/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - **Thực hành tổng hợp:** <br>&emsp; + Tạo Launch Template <br>&emsp; + Tạo Elastic Load Balancer <br>&emsp; + Khởi tạo Auto Scaling Group <br>&emsp; + Kiểm thử scaling (increase/decrease load) <br>&emsp; + Theo dõi CloudWatch metrics                                                                                         | 17/10/2025   | 17/10/2025      | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 6:

* **Thứ 2 (13/10/2025):**
  * Hiểu Auto Scaling Group (ASG) và các lợi ích chính:
    * Tính sẵn sàng cao - thay thế instance bị lỗi tự động
    * Khả năng mở rộng linh hoạt - tăng/giảm số lượng instance dựa trên nhu cầu
    * Phân phối tải hiệu quả với Elastic Load Balancer
    * Tiết kiệm chi phí - chỉ sử dụng đúng số lượng tài nguyên cần thiết
    * Tự động hóa cao
  * Hiểu Elastic Load Balancer và vai trò trong hệ thống

* **Thứ 3 (14/10/2025):**
  * Tìm hiểu Launch Template:
    * Khái niệm và mục đích của Launch Template
    * Cách tạo Launch Template từ EC2 instance hiện có
    * Cấu hình Launch Template (AMI, Instance Type, Key Pair, Security Groups)
  * Thực hành khởi tạo Launch Template
  * Cấu hình Security Groups cho Launch Template

* **Thứ 4 (15/10/2025):**
  * Tìm hiểu Elastic Load Balancer:
    * Các loại Load Balancer (ALB, NLB, CLB)
    * Health Checks - kiểm tra tình trạng instance
    * Target Groups - nhóm instance nhận traffic
    * Routing rules
  * Thực hành tạo Elastic Load Balancer
  * Cấu hình Target Groups
  * Kiểm thử Load Balancer hoạt động

* **Thứ 5 (16/10/2025):**
  * Khởi tạo Auto Scaling Group:
    * Cấu hình min/max/desired capacity
    * Cấu hình scaling policies (scale up/down)
    * Thiết lập metrics dựa trên CloudWatch (CPU, RAM, Network)
    * Kết nối ASG với Load Balancer
  * Hiểu Amazon CloudWatch:
    * Dịch vụ theo dõi và quản lý
    * Metrics và Logs
    * Lưu trữ dữ liệu 15 tháng
    * Tính toán trên metrics
  * Tìm hiểu CloudWatch Container Insights

* **Thứ 6 (17/10/2025):**
  * Thực hành tổng hợp triển khai toàn bộ giải pháp:
    * Tạo Launch Template từ ứng dụng FCJ Management
    * Tạo Elastic Load Balancer với Health Checks
    * Khởi tạo Auto Scaling Group
    * Kiểm thử scaling - tăng tải để ASG tự động tăng instance
    * Kiểm thử scaling - giảm tải để ASG tự động giảm instance
    * Theo dõi CloudWatch metrics (CPU, Network, request count)
    * Xác minh cân bằng tải - yêu cầu được phân phối đều giữa các instance
    * Dọn dẹp tài nguyên (ASG, Load Balancer, Launch Template)


