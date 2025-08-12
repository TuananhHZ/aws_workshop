---
title : "Tổng quan Runbook"
date: 2025-08-07
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---



## 1. Mục tiêu
Cung cấp quy trình từng bước để giám sát, phát hiện, và xử lý sự cố cơ sở dữ liệu một cách tự động, giúp giảm thiểu thời gian gián đoạn và nâng cao hiệu suất hệ thống.
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git5.runbook/5.1/5.1.4.png)

   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/5.runbook/5.1/5.1.5.png)

## 2. Phạm vi
Runbook này áp dụng cho:
- Các hệ thống cơ sở dữ liệu trên AWS (Amazon RDS, Aurora, DynamoDB…)
- Các môi trường Production, Staging, và Development
- Hỗ trợ nhiều loại cơ sở dữ liệu (MySQL, PostgreSQL, SQL Server…)

## 3. Kiến trúc hệ thống
- **Monitoring**: AWS CloudWatch, Performance Insights, Enhanced Monitoring
- **Alerting**: CloudWatch Alarms, SNS (Simple Notification Service)
- **Automation**: AWS Lambda, Systems Manager Automation
- **Dashboard**: CloudWatch Dashboards hoặc Grafana

## 4. Quy trình vận hành

### Bước 1: Giám sát (Monitoring)
- Kích hoạt Enhanced Monitoring trên RDS
- Bật Performance Insights để phân tích truy vấn
- Thu thập các metric: CPUUtilization, FreeableMemory, DatabaseConnections, DiskQueueDepth…

### Bước 2: Cấu hình cảnh báo (Alerting)
- Tạo CloudWatch Alarms với ngưỡng phù hợp
- Kết nối với SNS topic để gửi cảnh báo qua Email/SMS/ChatOps
- Phân loại cảnh báo theo mức độ (Warning, Critical)

### Bước 3: Tự động khắc phục (Automated Remediation)
- Sử dụng AWS Lambda để tự động thực hiện hành động khắc phục (VD: mở rộng instance, xóa kết nối treo, tăng IOPS…)
- Triển khai Systems Manager Automation Document (SSM Document) để chuẩn hóa thao tác

### Bước 4: Xử lý thủ công khi cần thiết
- Sử dụng Runbook để hướng dẫn kỹ thuật viên xác định nguyên nhân
- Truy cập Performance Insights để phân tích truy vấn chậm
- Kiểm tra logs từ RDS hoặc CloudWatch Logs

### Bước 5: Báo cáo và tối ưu
- Lập báo cáo hàng tuần về số lượng cảnh báo, thời gian xử lý và nguyên nhân
- Điều chỉnh ngưỡng cảnh báo và chính sách tự động để giảm cảnh báo giả

## 5. Quy tắc an toàn
- Mọi hành động can thiệp trực tiếp vào cơ sở dữ liệu cần được ghi lại
- Thực hiện trên môi trường Staging trước khi áp dụng Production
- Đảm bảo quyền truy cập chỉ dành cho nhân sự có thẩm quyền

## 6. Tài liệu tham khảo
- [AWS RDS Monitoring Documentation](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/monitoring-overview.html)
- [AWS CloudWatch Alarms](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html)
- [AWS Systems Manager Automation](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-automation.html)
