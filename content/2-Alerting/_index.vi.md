---
title : "Tổng quan về Cảnh báo"
date: 2025-08-07
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---


 
### 1. Cảnh báo là gì?
- **Cảnh báo (Alerting)** là quá trình thông báo cho quản trị viên, kỹ sư DevOps hoặc đội hỗ trợ khi các điều kiện, ngưỡng hoặc mẫu nhất định được phát hiện trong **metric** hoặc **log** của hệ thống.  
- Nó đóng vai trò quan trọng trong việc duy trì **độ tin cậy của hệ thống** và **thời gian hoạt động (uptime)** bằng cách giúp **phát hiện nhanh** và **phản ứng kịp thời** với sự cố.  

- Mục tiêu chính của cảnh báo:  
  - Phát hiện sự cố sớm  
  - Giảm thiểu thời gian ngừng hoạt động  
  - Cung cấp thông báo có tính hành động (actionable)  
  - Tránh “alert fatigue” bằng cách đảm bảo cảnh báo phù hợp và không tràn lan  

---

### 2. Cách thức hoạt động của hệ thống cảnh báo
1. **Thu thập dữ liệu** – Thu thập metric, log, và trace từ các dịch vụ khác nhau (ví dụ: EC2, RDS, Lambda).  
2. **Đánh giá điều kiện** – Áp dụng quy tắc hoặc ngưỡng để phát hiện các sự kiện bất thường hoặc suy giảm hiệu suất.  
3. **Kích hoạt cảnh báo** – Nếu điều kiện được đáp ứng, một cảnh báo sẽ được tạo ra.  
4. **Gửi thông báo** – Cảnh báo được gửi đến các kênh như email, Slack, SNS, PagerDuty, v.v.  

---

### 3. Các loại cảnh báo phổ biến
- **Cảnh báo dựa trên ngưỡng**: Kích hoạt khi giá trị metric vượt quá giới hạn định sẵn (ví dụ: CPU > 80%).  
- **Cảnh báo phát hiện bất thường (anomaly detection)**: Kích hoạt khi hệ thống phát hiện các mẫu bất thường khác với xu hướng lịch sử.  
- **Cảnh báo dựa trên log**: Kích hoạt khi xuất hiện từ khóa hoặc mẫu lỗi nhất định trong log.  

---

### 4. Các nguyên tắc tốt nhất (Best Practices)
- Thiết lập ngưỡng dựa trên **dữ liệu lịch sử** và **SLA dịch vụ**.  
- Sử dụng nhiều cấp độ cảnh báo (Info, Warning, Critical).  
- Gom nhóm các cảnh báo liên quan để tránh spam thông báo.  
- Thường xuyên rà soát và cập nhật quy tắc cảnh báo.  

---
