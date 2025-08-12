---
title : " Bật và kiểm tra Amazon CloudWatch Logs"
date: 2025-08-07
weight : 2 
chapter : false
pre : " <b> 1.2 </b> "
---

## Bước 2: Bật và kiểm tra Amazon CloudWatch Logs 

### 1. Kiểm tra / bật log export trên RDS (nếu chưa bật)
- Truy cập **AWS Console** → **RDS** → **Databases** → chọn instance (`monitoringdb`) → **Modify**.      
- Tìm phần **Monitoring** hoặc **Additional configuration** (tuỳ giao diện) → **Log exports** / **CloudWatch Logs exports**.  
- Tick chọn:
  - **Error log**
  - **Slow query log** (hoặc các log phù hợp với engine: `error`, `slowquery`, `postgresql`, ...).  
- **Save / Apply changes** → có thể cần **Reboot** nếu thay đổi parameter yêu cầu khởi động lại.  
  
- **Với MySQL**: cần bật `slow_query_log = 1` và thiết lập `long_query_time` trong **DB parameter group** để log truy vấn chậm được xuất ra.  
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.2/1.2.1.png)
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.2/1.2.2.png)
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.2/1.2.3.png)
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.2/1.2.4.png)


---

### 2. Vào CloudWatch để xem Log groups
- **AWS Console** → **CloudWatch** → **Logs** → **Log groups**.  
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.1.png)


### 3. Tạo Metric Filter từ Logs

1. Trong **CloudWatch** → **Logs**, chọn log group 
2. Nhấn **Create metric filter**.  
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.2.png)


3. Nhập **Filter pattern**:  `ERROR` → Next
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.3.png)

### 4. Cấu hình:

- **Metric namespace**: `RDSLogs` (ví dụ)

- **Metric name**: `ErrorCount`

- **Metric value**: `1`

- Tạo metric filter, sau đó tạo **Alarm** cho metric `RDSLogs / ErrorCount`
- Nhấn **Next**:
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.4.png)
- Nhấn **Create metric filter**: 
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.5.png)
- Ta được như sau: 
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.6.png)

### 5. Truy vấn nhanh lỗi
**Các bước thực hiện**:

- Vào **CloudWatch** → **Logs Insights**.
1. Chọn log group.
2. Nhập truy vấn để lọc lỗi:
```sql
fields @timestamp, @message
| filter @message like /ERROR/
| sort @timestamp desc
| limit 50
```
3. Run query:
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.7.png)