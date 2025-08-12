---
title : "Tạo một RDS Database để giám sát"
date: 2025-08-07
weight : 1 
chapter : false
pre : " <b> 1.1 </b> "
---

## Bước 1: Tạo một RDS Database để giám sát



1. Truy cập vào [AWS Management Console](https://aws.amazon.com/console/) → **Dịch vụ** → **RDS**.  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.1/1.1.1.png)

2. Nhấn **Create Database** để bắt đầu khởi tạo một cơ sở dữ liệu mới.  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.1/1.1.2.png)

3. **Chọn Engine**:
   - Chọn **MySQL** hoặc **PostgreSQL** tùy theo nhu cầu.  
     ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.1/1.1.3.png)
   - **Template**: Chọn **Free Tier** để tránh phát sinh chi phí (áp dụng nếu bạn mới sử dụng AWS).  
     ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.1/1.1.4.png)

4. **Điền thông tin cơ bản**:
   - **DB Name (DB instance identifier)**: `monitoringdb`  
   - **Username**: ví dụ `admin`  
   - **Password**: nhập, ghi nhớ và lưu lại để sử dụng về sau.  
     ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.1/1.1.5.png)

5. **Bật các tùy chọn giám sát nâng cao** (nằm trong **Advanced settings**):
   - **Enable Enhanced Monitoring**  
   - **Enable Performance Insights**  
   - **Enable CloudWatch Logs exports** (chọn `error` và `slowquery`)  
     ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.1/1.1.6.png)

6. Nhấn **Create Database** để AWS bắt đầu khởi tạo.  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.1/1.1.7.png)

   - Trạng thái sẽ là **Creating**, và khi chuyển sang **Available**, máy chủ cơ sở dữ liệu đã sẵn sàng sử dụng.  
     ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.1/1.1.8.png)
