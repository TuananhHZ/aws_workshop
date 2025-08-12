---
title : "Tạo cảnh báo CPU cao"
date: 2025-08-07
weight : 5 
chapter : false
pre : " <b> 2.1 </b> "
---



## Bước 5 – Tạo cảnh báo CPU cao

**Mục tiêu:** Cảnh báo khi CPU của RDS > 80% liên tục trong 5 phút.

---

### 1. Mở CloudWatch
1. Trong **AWS Console**, tìm **CloudWatch**.  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.1.png)
2. Ở menu bên trái, chọn **Alarms** → **Create alarm**.  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.1.png)

---

### 2. Chọn Metric
1. Nhấn **Select metric**.  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.2.png)

2. Điều hướng đến **RDS** → **Per-Database Metrics**.  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.3.png)
  
3. Chọn **DB instance** của bạn.  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.4.png)

4. Tìm và chọn **CPUUtilization** → nhấn **Select metric**.  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.5.png)

---

### 3. Cấu hình điều kiện cảnh báo
- **Statistic:** Average  
- **Period:** 1 minute *(hoặc 5 minutes nếu muốn giảm tần suất cảnh báo)*  
- **Threshold type:** Static  
- **Condition:** Greater than  
- **Threshold value:** `80`  
- **Evaluation period:** Chọn **for 5 consecutive periods** để yêu cầu CPU > 80% trong 5 phút liên tục.  
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.6.png)

---

### 4. Cấu hình hành động (Actions)
1. Trong **In alarm**, chọn **Send a notification to an SNS topic**.
2. Nếu chưa có topic, nhấn **Create new topic**:
   - **Name:** `rds-cpu-alert`
   - **Subscription:** Email → nhập email để nhận cảnh báo.  
     ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.7.png)

3. AWS sẽ gửi email xác nhận → **nhấn vào link Confirm** để kích hoạt nhận cảnh báo.  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.8.png)

---

### 5. Đặt tên & tạo Alarm
1. **Name:** `RDS-High-CPU-Alarm`
2. Nhấn **Review** → **Create alarm**.  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.9.png)  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.10.png)

---
