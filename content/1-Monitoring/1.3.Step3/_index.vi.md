---
title : "Quan sát metrics real-time và Performance Insights"
date: 2025-08-07
weight : 3
chapter : false
pre : " <b> 1.3 </b> "
---



## Bước 3: Quan sát metrics real-time và Performance Insights
### Xem metrics real-time trên CloudWatch
1. Truy cập **AWS Console** → **CloudWatch** → **Metrics**. 
2. Chọn **Browse** → **RDS** → **Per-Database Metrics**.
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.8.png)

3. Chọn **DBInstanceIdentifier** `monitoringdb-1`.
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.9.png)


4. Tick các metrics quan trọng:
- **CPUUtilization**
- **FreeableMemory**
- **ReadIOPS, WriteIOPS**
- **DatabaseConnections**
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.10.png)

5. Nhấn **Add to dashboard** nếu muốn hiển thị trực tiếp trên dashboard.
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.11.png)