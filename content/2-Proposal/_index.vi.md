---
title: "Bản đề xuất"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

Tại phần này, bạn cần tóm tắt các nội dung trong workshop mà bạn **dự tính** sẽ làm.

# FitChallenge  
## Ứng dụng hỗ trợ người dùng giảm cân dựa trên các thử thách về bài tập thể dục, có tích hợp AI để theo dõi, đánh giá.

### 1. Tóm tắt điều hành 
FitChallenge là ứng dụng di động được phát triển dành cho người Việt Nam, nhằm thúc đẩy phong trào tập luyện thể dục thể hình thông qua các thử thách thể thao có yếu tố gamification và trí tuệ nhân tạo (AI). Ứng dụng sử dụng AI Camera để nhận diện và đếm động tác tập luyện như push-up, squat, plank, jumping jack, đồng thời phân tích tư thế nhằm đưa ra đánh giá chính xác.
Người dùng có thể tham gia thử thách cá nhân để nhận điểm thưởng FitPoints khi hoàn thành nhiệm vụ, và quy đổi chúng thành voucher, quà tặng, hoặc ưu đãi từ các đối tác thương mại. FitChallenge hướng đến đối tượng sinh viên, giới trẻ, và người đi làm — những người cần động lực duy trì thói quen tập luyện trong cuộc sống bận rộn.

### 2. Tuyên bố vấn đề 
*Vấn đề hiện tại*  
Tại Việt Nam, các ứng dụng tập luyện hiện có phần lớn tập trung vào hướng dẫn hoặc đếm bước cơ bản, chưa có nền tảng nào kết hợp giữa AI nhận diện động tác, gamification và cộng đồng thử thách thể thao online.
Người dùng thường thiếu động lực để tập đều đặn, không có công cụ đánh giá chính xác hiệu suất tập luyện. Ngoài ra, các phòng gym hoặc thương hiệu thể thao cũng thiếu kênh tương tác sáng tạo với nhóm khách hàng trẻ năng động. 

*Giải pháp*  
FitChallenge tích hợp AI Camera trên thiết bị di động để nhận diện, đếm và đánh giá độ chính xác của động tác tập luyện thông qua Computer Vision.
Toàn bộ dữ liệu tập luyện của người dùng được lưu trữ và xử lý qua AWS Cloud với kiến trúc serverless:

AWS Lambda / EC2: xử lý dữ liệu AI và yêu cầu backend.
AWS S3: lưu trữ video, hình ảnh, và kết quả tạm thời.
AWS DynamoDB hoặc RDS: quản lý thông tin người dùng, điểm thưởng và kết quả.
AWS Rekognition Custom Labels (tùy chọn): huấn luyện mô hình nhận diện động tác nâng cao.
Ứng dụng di động được phát triển bằng Flutter hoặc React Native, giao diện thân thiện, trực quan, và hỗ trợ đa nền tảng (Android/iOS). Người dùng có thể:
Tham gia thử thách cá nhân, nhóm hoặc toàn quốc.
Nhận FitPoints khi hoàn thành bài tập.
Đổi FitPoints lấy voucher hoặc quà từ đối tác (Shopee, Grab, CGV,…).
Theo dõi bảng xếp hạng và chia sẻ thành tích lên mạng xã hội.

*Lợi ích và hoàn vốn đầu tư (ROI)*  
Đối với người dùng:
Tạo động lực luyện tập mỗi ngày thông qua cơ chế thử thách và phần thưởng.
Được AI hỗ trợ đánh giá và ghi nhận thành tích minh bạch.
Gắn kết cộng đồng tập luyện thông qua leaderboard và feed chia sẻ.
Đối với doanh nghiệp đối tác:
Kênh quảng bá thương hiệu gắn liền với lối sống lành mạnh.
Tiếp cận tệp khách hàng trẻ – năng động – có ý thức về sức khỏe.
Đối với đội ngũ phát triển:
Mở ra mô hình kinh doanh “Fitness + Gamification + Thương mại điện tử” độc đáo tại Việt Nam.
Cấu trúc cloud serverless giúp giảm chi phí vận hành và dễ mở rộng.
MVP có thể phát triển trong 3 tháng đầu, với chi phí hạ tầng thấp (ước tính 0,80 USD/tháng trên AWS). 

### 3. Kiến trúc giải pháp  
Nền tảng áp dụng kiến trúc AWS Serverless để quản lý dữ liệu từ 5 trạm dựa trên Raspberry Pi, có thể mở rộng lên 15 trạm. Dữ liệu được tiếp nhận qua AWS IoT Core, lưu trữ trong S3 data lake và xử lý bởi AWS Glue Crawlers và ETL jobs để chuyển đổi và tải vào một S3 bucket khác cho mục đích phân tích. Lambda và API Gateway xử lý bổ sung, trong khi Amplify với Next.js cung cấp bảng điều khiển được bảo mật bởi Cognito.  

![FitChallenge Station Architecture](/images/2-Proposal/edge_architecture.png)

![FitChallenge Platform Architecture](/images/2-Proposal/platform_architecture.png)

*Dịch vụ AWS sử dụng*  
- *AWS IoT Core*: Tiếp nhận dữ liệu MQTT từ 5 trạm, mở rộng lên 15.  
- *AWS Lambda*: Xử lý dữ liệu và kích hoạt Glue jobs (2 hàm).  
- *Amazon API Gateway*: Giao tiếp với ứng dụng web.  
- *Amazon S3*: Lưu trữ dữ liệu thô (data lake) và dữ liệu đã xử lý (2 bucket).  
- *AWS Glue*: Crawlers lập chỉ mục dữ liệu, ETL jobs chuyển đổi và tải dữ liệu.  
- *AWS Amplify*: Lưu trữ giao diện web Next.js.  
- *Amazon Cognito*: Quản lý quyền truy cập cho người dùng phòng lab.  

*Thiết kế thành phần*  
- *Thiết bị biên*: Raspberry Pi thu thập và lọc dữ liệu cảm biến, gửi tới IoT Core.  
- *Tiếp nhận dữ liệu*: AWS IoT Core nhận tin nhắn MQTT từ thiết bị biên.  
- *Lưu trữ dữ liệu*: Dữ liệu thô lưu trong S3 data lake; dữ liệu đã xử lý lưu ở một S3 bucket khác.  
- *Xử lý dữ liệu*: AWS Glue Crawlers lập chỉ mục dữ liệu; ETL jobs chuyển đổi để phân tích.  
- *Giao diện web*: AWS Amplify lưu trữ ứng dụng Next.js cho bảng điều khiển và phân tích thời gian thực.  
- *Quản lý người dùng*: Amazon Cognito giới hạn 5 tài khoản hoạt động.  

### 4. Triển khai kỹ thuật  
*Các giai đoạn triển khai*  
Dự án gồm 2 phần — thiết lập trạm thời tiết biên và xây dựng nền tảng thời tiết — mỗi phần trải qua 4 giai đoạn:  
1. *Nghiên cứu và vẽ kiến trúc*: Nghiên cứu Raspberry Pi với cảm biến ESP32 và thiết kế kiến trúc AWS Serverless (1 tháng trước kỳ thực tập).  
2. *Tính toán chi phí và kiểm tra tính khả thi*: Sử dụng AWS Pricing Calculator để ước tính và điều chỉnh (Tháng 1).  
3. *Điều chỉnh kiến trúc để tối ưu chi phí/giải pháp*: Tinh chỉnh (ví dụ tối ưu Lambda với Next.js) để đảm bảo hiệu quả (Tháng 2).  
4. *Phát triển, kiểm thử, triển khai*: Lập trình Raspberry Pi, AWS services với CDK/SDK và ứng dụng Next.js, sau đó kiểm thử và đưa vào vận hành (Tháng 2–3).  

*Yêu cầu kỹ thuật*  
- *Trạm thời tiết biên*: Cảm biến (nhiệt độ, độ ẩm, lượng mưa, tốc độ gió), vi điều khiển ESP32, Raspberry Pi làm thiết bị biên. Raspberry Pi chạy Raspbian, sử dụng Docker để lọc dữ liệu và gửi 1 MB/ngày/trạm qua MQTT qua Wi-Fi.  
- *Nền tảng thời tiết*: Kiến thức thực tế về AWS Amplify (lưu trữ Next.js), Lambda (giảm thiểu do Next.js xử lý), AWS Glue (ETL), S3 (2 bucket), IoT Core (gateway và rules), và Cognito (5 người dùng). Sử dụng AWS CDK/SDK để lập trình (ví dụ IoT Core rules tới S3). Next.js giúp giảm tải Lambda cho ứng dụng web fullstack.  

### 5. Lộ trình & Mốc triển khai  
- *Trước thực tập (Tháng 0)*: 1 tháng lên kế hoạch và tìm hiểu kiến thức liên quan.  
- *Thực tập (Tháng 1–3)*:  
    - Tháng 1: Học AWS và phát thảo sơ bộ quy trình làm dự án.  
    - Tháng 2: Thiết kế và điều chỉnh kiến trúc.  
    - Tháng 3: Triển khai, kiểm thử, đưa vào sử dụng.  
- *Sau triển khai*: Nghiên cứu thêm trong vòng 1 năm.  

### 6. Ước tính ngân sách  
Có thể xem chi phí trên [AWS Pricing Calculator](https://calculator.aws/#/estimate?id=621f38b12a1ef026842ba2ddfe46ff936ed4ab01)  
Hoặc tải [tệp ước tính ngân sách](../attachments/budget_estimation.pdf).  

*Chi phí hạ tầng*   
- AWS Amplify: 0,75 USD/tháng (20 GB data served, build ~50 phút)
- AWS Lambda + API Gateway: 0,00 USD/tháng (150.000 requests, 15.000 GB-s tính toán)
- SageMaker Serverless: 0,00 USD/tháng (45.000 GB-s) 
- DynamoDB: 0,00 USD/tháng (100.000 đọc, 20.000 ghi)
- Cognito: 0,00 USD/tháng (1000 MAU)
- Amazon S3 (Model): 0,00 USD/tháng (0,05 GB lưu trữ)
- Amazon S3 (Media): 0,05 USD/tháng (5 GB lưu trữ, 50.000 GET, 10.000 PUT)
- CloudWatch: 0,00 USD/tháng (2 GB logs, 5 GB lưu trữ)


*Tổng*: 0,8 USD/tháng, 9,60 USD/12 tháng  

### 7. Đánh giá rủi ro  
*Ma trận rủi ro*  
- Kỹ thuật: AI nhận diện sai động tác hoặc lỗi xử lý dữ liệu ảnh/video.
- Người dùng: Không duy trì thói quen luyện tập, không giữ chân được người dùng.
- Thị trường & Đối tác: Khó mở rộng mạng lưới đối tác thưởng và thương hiệu đồng hành.

*Chiến lược giảm thiểu*  
- Tối ưu mô hình AI qua huấn luyện liên tục và định kỳ. Ngoài ra có thể xin phép được sử dụng video của người dùng để cải thiện hiệu suất mô hình.
- Triển khai gamification sâu hơn (chuỗi streak, nhóm bạn, phần thưởng hấp dẫn).
- Tìm hiểu kỹ các đối tác và trình bày rõ giá trị hợp tác để có thể thiết lập hợp đồng lâu dài.

*Kế hoạch dự phòng*  
- Khi AI gặp lỗi → thêm hệ thống fallback để dùng các phiên bản mô hình khác nhau.
- Khi lượng người dùng giảm → tung thử thách cộng đồng theo mùa, thêm vouchers vào các dịp đặc biệt (Lễ, Tết, Hè,...).
- Khi đối tác thương mại rút lui → duy trì cơ chế FitPoints nội bộ đổi quà nhỏ để đi tìm đối tác thay thế.

### 8. Kết quả kỳ vọng  
*Cải tiến kỹ thuật*: 
- Hoàn thiện hệ thống AI nhận diện động tác có độ chính xác >90%.
- Ứng dụng ổn định, đáp ứng 10.000 người dùng hoạt động đồng thời.
- Tối ưu kiến trúc serverless giúp chi phí hạ tầng duy trì dưới 1 USD/tháng trong giai đoạn MVP.

*Giá trị dài hạn*: 
- Xây dựng cộng đồng người Việt yêu thích thể thao và sức khỏe bền vững.
- Trở thành nền tảng tiên phong “AI + Fitness + Gamification” tại Việt Nam.