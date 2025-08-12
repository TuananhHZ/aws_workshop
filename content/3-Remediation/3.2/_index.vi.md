---
title : "Tạo rule gọi Lambda khi alarm kích hoạt"
date: 2025-08-07
weight : 2 
chapter : false
pre : " <b> 3.2. </b> "
---



## Bước 8: Tạo rule gọi Lambda khi alarm kích hoạt

### 1. Mở EventBridge
- Vào **AWS Management Console** → tìm **EventBridge** → **Rules** → **Create rule**.
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.2/3.2.1.png)
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.2/3.2.2.png)
---

### 2. Thông tin rule
- **Name**: `auto-reboot-on-highcpu-2` (hoặc tên bạn muốn).
- **Event bus**: `default`.
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.2/3.2.3.png)
---

### 3. Chọn Event Source
- **AWS events or EventBridge partner events**.
- **Event source**: `AWS services`.
- **Service name**: `CloudWatch`.
- **Event type**: `CloudWatch Alarm State Change`.
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.2/3.2.5.png)
---

### 4. Filter alarm cần bắt
Trong phần **pattern**, chọn điều kiện sau:

```json
{
  "source": ["aws.cloudwatch"],
  "detail-type": ["CloudWatch Alarm State Change"],
  "detail": {
    "alarmName": ["HighCPUAlarm"],
    "state": {
      "value": ["ALARM"]
    }
  }
}
```
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.2/3.2.6.png)

5. Chọn target
- **Target type**: `Lambda function`
- Chọn **Lambda function** vừa tạo (`rds-auto-reboot`)
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.2/3.2.7.png)
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.2/3.2.8.png)

6. Tạo rule
- Nhấn **Create** để hoàn tất.
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.2/3.2.9.png)

7. Kết quả
- Khi **alarm** kích hoạt, **Lambda** sẽ tự động **reboot DB**.