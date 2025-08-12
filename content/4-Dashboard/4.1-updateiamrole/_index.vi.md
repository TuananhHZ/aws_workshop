---
title :  "Tạo CloudWatch Dashboard"
date: 2025-08-07
weight : 1 
chapter : false
pre : " <b> 4.1 </b> "
---



### Bước 9: Tạo CloudWatch Dashboard  
**Mục tiêu**: Có một bảng điều khiển trực quan để theo dõi trạng thái **RDS database** và các chỉ số quan trọng.

---

#### 1. Mở CloudWatch Dashboards  
- Đăng nhập **AWS Management Console**.  
- Tìm **CloudWatch** trong thanh tìm kiếm và mở nó.  
- Trong menu bên trái, chọn **Dashboards**.  
- Nhấn **Create dashboard**.  
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/4.dashboard/4.1/4.1.1.png)
---

#### 2. Đặt tên Dashboard  
- Nhập tên, ví dụ: `RDS-Monitoring-Dashboard`.  
- Nhấn **Create dashboard**.  
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/4.dashboard/4.1/4.1.2.png)

---

#### 3. Thêm Widgets  
##### **Widget 1: CPU Utilization**  
- Chọn **Line** (hoặc **Number** nếu muốn dạng số realtime).  
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/4.dashboard/4.1/4.1.9.png)

- Chọn **Next**.  
- Trong **Browse**, chọn:  
  - `RDS → DB Instance → <tên database>`  
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/4.dashboard/4.1/4.1.4.png)
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/4.dashboard/4.1/4.1.5.png)

  - **Metric**: `CPUUtilization` 
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/4.dashboard/4.1/4.1.6.png) 

- Nhấn **Create widget**.  
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/4.dashboard/4.1/4.1.7.png)
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/4.dashboard/4.1/4.1.8.png)

+ Các **Metric** tiếp theo thực hiện tương tự:
  - **Metric**: `FreeableMemory`  
  - **Metric**: `ReadIOPS`  
  - **Metric**: `WriteIOPS`  
  - **Metric**: `DatabaseConnections`  
+ Sắp xếp các **Metric** cho phù hợp:
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/4.dashboard/4.1/4.1.13.png)