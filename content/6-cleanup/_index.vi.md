---
title : "Dọn Dẹp Tài Nguyên"
date: 2025-08-07
weight : 6 
chapter : false
pre : " <b> 6. </b> "
---


## **BƯỚC 1: Xóa các cảnh báo (CloudWatch Alarms)**
1. Truy cập **AWS Console** → tìm và mở dịch vụ **CloudWatch**.  
2. Ở menu bên trái, chọn **Alarms**.  
3. Tick chọn tất cả các cảnh báo đã tạo (ví dụ: `CPUUtilization`, `ReadIOPS`, `WriteIOPS`, `DatabaseConnections`).  
4. Nhấn **Actions** → **Delete**.  
5. Xác nhận bằng cách chọn **Delete**.  
    ![cleanup](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/6.clean/6.1.1.png)
    ![cleanup](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/6.clean/6.1.2.png)

> 📌 **Lý do:** Nếu giữ alarm thì CloudWatch vẫn tính chi phí giám sát.

---

## **BƯỚC 2: Xóa Dashboard hoặc Widget theo dõi**
1. Trong **CloudWatch**, vào mục **Dashboards**.  
2. Chọn dashboard đã tạo (ví dụ: `RDS-Monitoring`).  
3. Nhấn **Actions** → **Delete dashboard**.  
4. Xác nhận **Delete**.  
    ![cleanup](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/6.clean/6.1.3.png)
    ![cleanup](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/6.clean/6.1.5.png)


> 📌 **Lý do:** Dashboard không tốn nhiều chi phí nhưng nên dọn cho gọn.

---

## **BƯỚC 3: Xóa hoặc dừng RDS Instance**
- Nếu muốn giữ dữ liệu, hãy tạo **Final Snapshot** trước khi xóa.

**Cách xóa:**
1. Truy cập **AWS Console** → **RDS**.  
2. Chọn DB instance đã dùng (ví dụ: `monitoringdb`).  
3. Nhấn **Actions** → **Delete**.  
4. Chọn **Create final snapshot** nếu muốn lưu dữ liệu.  
5. Chọn **Retain automated backups** hoặc bỏ tick nếu không cần.  
6. Gõ `delete me` vào ô xác nhận.  
7. Nhấn **Delete**.  
    ![cleanup](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/6.clean/6.2.1.png)
    ![cleanup](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/6.clean/6.2.2.png)

> 📌 **Lưu ý:** Nếu chỉ muốn tạm dừng để thử nghiệm sau, chọn **Stop** thay vì **Delete**.

---

## **BƯỚC 4: Xóa Snapshot nếu không còn cần**
1. Trong **RDS**, vào **Snapshots**.  
2. Tick chọn snapshot không cần.  
3. Nhấn **Actions** → **Delete snapshot** → **Delete**.  
    ![cleanup](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/6.clean/6.3.1.png)
    ![cleanup](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/6.clean/6.3.2.png)

> 📌 **Lý do:** Snapshot chiếm dung lượng lưu trữ S3 và tính phí hàng tháng.

---

## **BƯỚC 5: Xóa Security Group / Parameter Group tùy chỉnh**
**Security Group**
1. Vào **EC2** → **Security Groups**.  
2. Chọn nhóm bảo mật chỉ dùng cho workshop.  
3. Nhấn **Actions** → **Delete security group**.  
     ![cleanup](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/6.clean/6.4.1.png)
**Parameter Group**
1. Vào **RDS** → **Parameter groups**.  
2. Chọn parameter group đã tạo riêng.  
3. Nhấn **Delete**.  
   

> 📌 **Lý do:** Nếu không dùng nữa, nên xóa để gọn gàng và tránh nhầm lẫn.

---

## **BƯỚC 6: Kiểm tra Billing**
1. Vào **Billing Dashboard** trong **AWS Console**.  
2. Xem mục **Bills** → **Current month** để chắc chắn không còn dịch vụ nào tính phí.  
3. Kiểm tra **Cost Explorer** để đảm bảo không có tài nguyên chạy ngầm.
