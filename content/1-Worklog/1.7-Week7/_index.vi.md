---
title: "Worklog Tuần 7"
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

* Tìm hiểu Amazon Route 53 - dịch vụ DNS của AWS
* Xây dựng hệ thống DNS hybrid - tích hợp on-premise DNS với Route 53
* Tìm hiểu Route 53 Resolver (Outbound, Inbound Endpoints và Rules)
* Tìm hiểu AWS Command Line Interface (AWS CLI)
* Cấu hình và sử dụng AWS CLI
* Thực hành với Route 53 và AWS CLI

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Giới thiệu Amazon Route 53 <br>&emsp; + Khái niệm DNS và Route 53 <br>&emsp; + Các tính năng của Route 53 <br>&emsp; + Đăng ký miền DNS, tạo vùng DNS riêng <br> - Giới thiệu AWS CLI                                            | 20/10/2025   | 20/10/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Tìm hiểu Route 53 Resolver <br>&emsp; + Outbound Endpoints - truy vấn tới DNS on-premise <br>&emsp; + Inbound Endpoints - nhận truy vấn từ on-premise <br> - **Thực hành:** <br>&emsp; + Tạo VPC và Resolver Endpoints | 21/10/2025   | 21/10/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Tìm hiểu Route 53 Resolver Rules <br>&emsp; + Cấu hình chuyển tiếp DNS <br>&emsp; + Forward rules tới DNS on-premise <br> - Thiết lập DNS hybrid architecture <br> - **Thực hành:** <br>&emsp; + Tạo Resolver Rules | 22/10/2025   | 22/10/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Cấu hình AWS CLI <br>&emsp; + Cài đặt AWS CLI <br>&emsp; + aws configure - thiết lập credentials <br>&emsp; + Cấu hình Region và Output Format <br>&emsp; + Profile trong AWS CLI <br> - Tìm hiểu khả năng của AWS CLI                  | 23/10/2025   | 23/10/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - **Thực hành tổng hợp:** <br>&emsp; + Cấu hình AWS CLI (default profile) <br>&emsp; + Sử dụng AWS CLI để quản lý Route 53 (list domains, zones) <br>&emsp; + Sử dụng AWS CLI quản lý EC2, RDS, S3 <br>&emsp; + Tạo shell scripts với AWS CLI <br>&emsp; + So sánh output formats (json, table, yaml, text)                                                                                         | 24/10/2025   | 24/10/2025      | <https://cloudjourney.awsstudygroup.com/> |


### Kết quả đạt được tuần 7:

* **Thứ 2 (20/10/2025):**
  * Hiểu Amazon Route 53 - dịch vụ DNS quản lý của AWS
  * Nắm rõ các tính năng của Route 53:
    * Đăng ký miền DNS công cộng
    * Tạo vùng DNS riêng (Private Hosted Zones)
    * Phân giải tên miền
    * Kiến trúc DNS hybrid
  * Hiểu khái niệm AWS CLI và mục đích sử dụng
  * Biết AWS CLI là công cụ mã nguồn mở tương tác với AWS

* **Thứ 3 (21/10/2025):**
  * Hiểu Route 53 Resolver và ba công cụ chính:
    * **Outbound Endpoints**: Gửi truy vấn DNS từ Route 53 tới DNS on-premise
    * **Inbound Endpoints**: Nhận truy vấn DNS từ on-premise về Route 53
    * **Resolver Rules**: Cấu hình chuyển tiếp DNS
  * Hiểu kiến trúc DNS hybrid
  * Thực hành tạo VPC và Resolver Endpoints

* **Thứ 4 (22/10/2025):**
  * Tìm hiểu Route 53 Resolver Rules:
    * Cấu hình chuyển tiếp (forwarding) cho tên miền cụ thể
    * Forward rules tới DNS server on-premise
    * Conditional forwarding rules
  * Thiết lập DNS hybrid architecture
  * Thực hành tạo Resolver Rules

* **Thứ 5 (23/10/2025):**
  * Cài đặt AWS CLI:
    * Hỗ trợ Linux, macOS, Windows
    * Cài đặt từ pip hoặc package manager
  * Cấu hình AWS CLI cơ bản:
    * Sử dụng `aws configure` command
    * Nhập Access Key ID
    * Nhập Secret Access Key
    * Chọn Default Region
    * Chọn Output Format
  * Hiểu Profiles trong AWS CLI:
    * Default profile
    * Tạo multiple profiles với `--profile` option
    * Lưu trữ trong config và credentials files
  * Tìm hiểu khả năng của AWS CLI:
    * Truy cập API công khai của AWS
    * Quản lý tài nguyên qua command line
    * Viết shell scripts tự động hóa

* **Thứ 6 (24/10/2025):**
  * Thực hành cấu hình AWS CLI (default profile)
  * Sử dụng AWS CLI quản lý Route 53:
    * `aws route53 list-hosted-zones`
    * `aws route53 list-resource-record-sets`
  * Sử dụng AWS CLI quản lý EC2:
    * `aws ec2 describe-instances`
    * `aws ec2 describe-security-groups`
  * Sử dụng AWS CLI quản lý RDS:
    * `aws rds describe-db-instances`
  * Sử dụng AWS CLI quản lý S3:
    * `aws s3 ls`
    * `aws s3 cp` commands
  * Viết shell scripts kết hợp AWS CLI commands
  * So sánh các output formats:
    * **json** - định dạng JSON (mặc định)
    * **table** - định dạng bảng trực quan
    * **yaml** - định dạng YAML
    * **text** - định dạng văn bản (tab-separated)
  * Thực hành filter và xử lý output từ AWS CLI


