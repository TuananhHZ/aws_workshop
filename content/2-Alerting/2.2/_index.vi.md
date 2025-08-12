---
title : "Tạo cảnh báo từ log error"
date: 2025-08-07
weight : 5 
chapter : false
pre : " <b> 2.2 </b> "
---



## Bước 6 – Tạo cảnh báo từ log error

**Mục tiêu:** Tạo cảnh báo khi log RDS chứa từ `"ERROR"` ít nhất 2 lần trong 5 phút.

---

### 1. Truy cập CloudWatch Logs
- Mở **AWS Console** → **CloudWatch** → **Logs** → **Log groups**.
- Tìm log group của RDS
- Nhấp vào log group.
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.1.png)
   
---

### 2. Tạo Metric Filter
1. Chọn **Create metric filter**.
2. Trong **Filter pattern**, nhập:
3. Chọn **Test pattern** để đảm bảo lọc đúng log chứa `ERROR`.
4. Nhấn **Next**.
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.2.png)
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.3.png)

---

### 3. Gán tên Metric
- **Metric name:** `ErrorCount`
- **Metric namespace:** `RDSLogs` (có thể tùy chỉnh).
- **Metric value:** `1`
- Nhấn **Create filter**.
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.4.png)
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.5.png)
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.6.png)
---

### 4. Tạo Alarm cho Metric
1. Sau khi metric filter được tạo, chọn **Create alarm**.
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.2/2.2.1.png)

2. **Điều kiện:** `ErrorCount > 1` trong **5 minutes**.
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.2/2.2.2.png)

3. **Actions:** Gửi thông báo qua **SNS** (có thể dùng chung topic email ở *Bước 5*).
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.2/2.2.3.png)
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.2/2.2.4.png)
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.2/2.2.5.png)
   

---
