---
title : " Tạo Lambda function xử lý "
date: 2025-08-07
weight : 1 
chapter : false
pre : " <b> 3.1. </b> "
---



### Bước 7 – Tạo Lambda function xử lý

#### **Mục tiêu**  
Tạo một Lambda function tự động reboot RDS khi cần.

---

#### **Mở Lambda**
- Vào **AWS Management Console** → tìm **Lambda** → **Create function**.
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.1.png)
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.2.png)

---

#### **Cấu hình ban đầu**
1. **Author from scratch** (tạo mới từ đầu).  
2. **Function name**: `rds-auto-reboot` *(hoặc tên bạn muốn)*.  
3. **Runtime**: `Python 3.12`.  
4. **Permissions**:  
   - Chọn **Create a new role with basic Lambda permissions**. 
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.3.png) 

> **Lưu ý**: Sau khi tạo xong, vào **IAM → Roles** để **thêm quyền** `AmazonRDSFullAccess` cho role này (để Lambda có thể reboot RDS)

   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.4.png)
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.5.png)
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.6.png)
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.7.png)

#### **Dán code xử lý**
Trong phần **Code editor** của Lambda, dán nội dung sau:
```python
import boto3

def lambda_handler(event, context):
    rds = boto3.client('rds')
    rds.reboot_db_instance(DBInstanceIdentifier='monitoringdb')
    return "Database rebooted"
```
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.8.png)
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.9.png)

4. Deploy & Test
- Nhấn Deploy để lưu code.
- Có thể Test thử bằng cách tạo event giả để chắc chắn Lambda chạy OK.
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.10.png)
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.11.png)
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.12.png)
