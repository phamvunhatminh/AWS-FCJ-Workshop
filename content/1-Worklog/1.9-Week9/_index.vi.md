---
title: "Worklog Tuần 9"
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

* Khởi động dự án nhóm: Ứng dụng luyện tập sức khỏe tích hợp AI
* Chốt ý tưởng và định hướng dự án
* Tìm hiểu các chỉ số cơ thể liên quan sức khỏe (BMR, TDEE, MET, PF)
* Hiểu các công thức tính lượng calo tiêu thụ và điều chỉnh theo mục tiêu
* Nghiên cứu các model AI có thể áp dụng (Amazon Bedrock) để tạo đề xuất cá nhân hóa
* Lập kế hoạch kiến trúc dự án sử dụng AWS services

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Khởi động dự án nhóm <br>&emsp; + Thảo luận ý tưởng chính: Ứng dụng luyện tập sức khỏe + AI <br>&emsp; + Xác định mục tiêu dự án <br>&emsp; + Chia nhóm công việc <br> - Tìm hiểu chỉ số BMR và công thức tính | 03/11/2025   | 03/11/2025      |
| 3   | - Tìm hiểu TDEE (Total Daily Energy Expenditure) <br>&emsp; + Tính Activity Multiplier theo mức độ hoạt động <br>&emsp; + Xác định mục tiêu người dùng (giảm cân, tăng cơ, giữ cân) <br> - **Thực hành:** <br>&emsp; + Tính TDEE cho các profile khác nhau | 04/11/2025   | 04/11/2025      |
| 4   | - Tìm hiểu MET (Metabolic Equivalent of Task) <br>&emsp; + Công thức tính calo từ bài tập <br>&emsp; + Các bài tập phổ biến và MET values <br> - Tìm hiểu công thức điều chỉnh bài tập theo mục tiêu | 05/11/2025   | 05/11/2025      |
| 5   | - Tìm hiểu chỉ số thể lực (Physical Fitness - PF) <br>&emsp; + Công thức tính PF từ height, weight, level, age, gender <br>&emsp; + Hệ số điều chỉnh bài tập dựa trên PF <br> - Tìm hiểu hệ số tăng tiến (progression rate) | 06/11/2025   | 06/11/2025      |
| 6   | - **Thực hành tổng hợp:** <br>&emsp; + Tính toán đầy đủ cho 1 user profile (BMR, TDEE, MET, PF) <br>&emsp; + Tạo spreadsheet/document tính toán health metrics <br>&emsp; + Lập kế hoạch kiến trúc dự án trên AWS <br>&emsp; + Tìm hiểu Amazon Bedrock cho AI recommendations | 07/11/2025   | 07/11/2025      |


### Kết quả đạt được tuần 9:

* **Thứ 2 (03/11/2025):**
  * Chốt ý tưởng dự án: Ứng dụng luyện tập sức khỏe tích hợp AI
  * Xác định các tính năng chính:
    * Theo dõi lượng calo tiêu thụ hàng ngày
    * Đề xuất bài tập dựa trên mục tiêu (giảm cân, tăng cơ, giữ cân)
    * Tạo thực đơn tối ưu bằng Amazon Bedrock AI
    * Theo dõi tiến độ thể lực qua các chỉ số
  * Chia nhóm công việc: Backend, Frontend, AI/ML, DevOps
  * Tìm hiểu BMR (Basal Metabolic Rate):
    * BMR = lượng năng lượng cơ thể sử dụng khi nghỉ ngơi
    * Công thức Nam: BMR = 10×weight(kg) + 6.25×height(cm) - 5×age + 5
    * Công thức Nữ: BMR = 10×weight(kg) + 6.25×height(cm) - 5×age - 161

* **Thứ 3 (04/11/2025):**
  * Hiểu TDEE (Total Daily Energy Expenditure):
    * TDEE = BMR × Activity Multiplier
  * Nắm rõ Activity Multiplier theo mức độ hoạt động:
    * Ít vận động: 1.2
    * Vận động nhẹ (1-3 buổi/tuần): 1.375
    * Trung bình (3-5 buổi/tuần): 1.55
    * Nhiều (6-7 buổi/tuần): 1.725
    * Rất nhiều (vận động viên): 1.9
  * Xác định mục tiêu điều chỉnh calo:
    * Giảm cân: TDEE - 500 kcal/ngày
    * Tăng cơ: TDEE + 300-500 kcal/ngày
    * Giữ cân: TDEE
  * Thực hành tính TDEE cho các profile khác nhau

* **Thứ 4 (05/11/2025):**
  * Hiểu MET (Metabolic Equivalent of Task):
    * MET = đơn vị đo cường độ hoạt động thể chất
    * Công thức tính calo: Calories = MET × Weight(kg) × Time(min)
  * Nắm các bài tập phổ biến với MET values:
    * Push-up: MET 8.0 (cường độ cao)
    * Squat: MET 5.0 (trung bình)
    * Jumping Jack: MET 9.0 (cardio mạnh)
    * Plank: MET 3.3 (giữ tĩnh, nhẹ hơn)
  * Hiểu cách tính lượng calo còn lại:
    * Calo còn lại = TDEE (điều chỉnh theo mục tiêu) - Calories (từ bài tập)
  * Tìm hiểu hệ số điều chỉnh bài tập theo mục tiêu:
    * Giảm cân: tăng 10% reps cardio
    * Tăng cơ: tăng 10% reps sức mạnh
    * Giữ dáng: giữ nguyên

* **Thứ 5 (06/11/2025):**
  * Hiểu chỉ số thể lực (PF - Physical Fitness):
    * PF = (height - 100) / weight × L × A × G
    * Khoảng giá trị: 0.4 - 1.5
  * Hiểu các thông số tính PF:
    * L (Fitness Level): Beginner=0.6, Intermediate=1.0, Advanced=1.3
    * A (Age): ≤30=1.0, 31-45=0.9, 46-60=0.8, >60=0.7
    * G (Gender): Nam=1.0, Nữ=0.85
  * Nắm rõ hệ số điều chỉnh bài tập dựa trên PF:
    * Push-up: 25 × PF
    * Squat: 35 × (PF + 0.1)
    * Jumping Jack: 100 × (PF + 0.2)
    * Plank: 40 × (PF + 0.1)
  * Hiểu công thức tăng tiến (progression): Sd = S1 × (1 + k)^(d-1)
    * k (rate): phụ thuộc vào level và duration lộ trình
    * Lộ trình: 7, 14, 21, 30, 60, 90 ngày

* **Thứ 6 (07/11/2025):**
  * Thực hành tính toán đầy đủ cho 1 user profile:
    * Bước 1: Tính BMR từ weight, height, age, gender
    * Bước 2: Tính TDEE từ BMR × Activity Multiplier
    * Bước 3: Điều chỉnh calo theo mục tiêu
    * Bước 4: Tính PF từ height, weight, level, age, gender
    * Bước 5: Tạo workout plan với reps điều chỉnh theo PF
    * Bước 6: Theo dõi progression theo công thức tăng tiến
  * Tạo spreadsheet/document để tính toán health metrics
  * Lập kế hoạch kiến trúc dự án trên AWS:
    * Frontend: React/Vue cho web app
    * Backend: Node.js/Python + Amazon RDS (user data)
    * AI/ML: Amazon Bedrock cho meal recommendations
    * Storage: S3 cho workout plans
    * Monitoring: CloudWatch cho tracking
  * Nghiên cứu Amazon Bedrock:
    * Sử dụng pre-trained AI models
    * Tạo personalized meal plans dựa trên calo còn lại
    * Fine-tune recommendations theo health goals


