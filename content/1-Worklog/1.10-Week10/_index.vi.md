---
title: "Worklog Tuần 10"
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

* Triển khai Mediapipe Pose Detection để theo dõi động tác thể dục
* Nghiên cứu và phát triển thuật toán dựa trên tọa độ pose (skeleton tracking)
* Kiểm tra và tinh chỉnh thuật toán để tối ưu hóa độ chính xác
* Tìm hiểu Amazon Bedrock để tích hợp AI trả lời câu hỏi về sức khỏe
* Tạo FE (Frontend) bằng TypeScript + React
* Tích hợp real-time pose tracking vào web application

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Giới thiệu Mediapipe Pose Detection <br>&emsp; + Cài đặt Mediapipe library <br>&emsp; + Tạo script cơ bản pose tracking <br>&emsp; + Visualize tọa độ skeleton trên video <br> - Tìm hiểu pose landmarks (x, y, z coordinates) | 10/11/2025   | 10/11/2025      |
| 3   | - Nghiên cứu thuật toán dựa trên tọa độ pose <br>&emsp; + Tính toán khoảng cách giữa các joints <br>&emsp; + Tính góc cổ tay (angles) <br>&emsp; + Nhận diện động tác (Push-up, Squat, Plank) <br> - **Thực hành:** <br>&emsp; + Viết code nhận diện Push-up | 11/11/2025   | 11/11/2025      |
| 4   | - Tiếp tục phát triển thuật toán <br>&emsp; + Nhận diện Squat, Plank <br>&emsp; + Tính rep count (số lần lặp) cho mỗi bài tập <br>&emsp; + Tính thời gian thực hiện <br> - Kiểm tra và tinh chỉnh độ chính xác | 12/11/2025   | 12/11/2025      |
| 5   | - Tìm hiểu Amazon Bedrock <br>&emsp; + Các available foundation models <br>&emsp; + Cách gọi Bedrock API <br>&emsp; + Tạo prompt cho health Q&A <br> - **Thực hành:** <br>&emsp; + Tạo chatbot trả lời câu hỏi sức khỏe | 13/11/2025   | 13/11/2025      |
| 6   | - Tìm hiểu TypeScript và React <br>&emsp; + Setup React project với TypeScript <br>&emsp; + Tạo components cho pose tracking UI <br>&emsp; + Tích hợp Mediapipe vào React <br>&emsp; + Tạo form nhập dữ liệu, đăng ký, đăng nhập <br>&emsp; + Tích hợp Bedrock API cho Chatbot | 14/11/2025   | 14/11/2025      |


### Kết quả đạt được tuần 10:

* Thứ 2 (10/11/2025):
  * Hiểu Mediapipe Pose Detection — theo dõi pose bằng ML
  * Cài đặt: `pip install mediapipe opencv-python`
  * Xây script cơ bản (webcam/file), detect 33 landmarks (x, y, z)
  * Visualize skeleton và xem confidence scores

* Thứ 3 (11/11/2025):
  * Phát triển thuật toán: khoảng cách khớp, góc khớp
  * Nhận diện Push‑up bằng ngưỡng góc khuỷu tay; đếm rep theo chuyển trạng thái down→up

* Thứ 4 (12/11/2025):
  * Mở rộng Squat và Plank; đếm rep từng bài
  * Tính thời lượng theo frames/FPS; tinh chỉnh ngưỡng, smoothing dữ liệu pose

* Thứ 5 (13/11/2025):
  * Tìm hiểu Amazon Bedrock; gọi Bedrock Runtime; tạo prompt chatbot sức khỏe

* Thứ 6 (14/11/2025):
  * Setup React + TypeScript; component UI pose tracking; tích hợp Mediapipe realtime
  * Backend gọi Bedrock; hiển thị khuyến nghị; UI gồm navbar, profile, start workout, chatbot sidebar, dashboard


