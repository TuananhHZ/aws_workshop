---
title : "Cleanup "
date: 2025-08-07
weight : 6 
chapter : false
pre : " <b> 6. </b> "
---


## **STEP 1: Delete CloudWatch Alarms**
1. Go to **AWS Console** → search for and open the **CloudWatch** service.  
2. In the left-hand menu, select **Alarms**.  
3. Tick all alarms created (e.g., `CPUUtilization`, `ReadIOPS`, `WriteIOPS`, `DatabaseConnections`).  
4. Click **Actions** → **Delete**.  
5. Confirm by selecting **Delete**.  
    ![cleanup](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/6.clean/6.1.1.png)  
    ![cleanup](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/6.clean/6.1.2.png)  

> 📌 **Reason:** Keeping alarms will still incur CloudWatch monitoring charges.

---

## **STEP 2: Delete Monitoring Dashboards or Widgets**
1. In **CloudWatch**, go to **Dashboards**.  
2. Select the dashboard created (e.g., `RDS-Monitoring`).  
3. Click **Actions** → **Delete dashboard**.  
4. Confirm **Delete**.  
    ![cleanup](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/6.clean/6.1.3.png)  
    ![cleanup](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/6.clean/6.1.5.png)  

> 📌 **Reason:** Dashboards don’t cost much, but cleaning them up keeps things organized.

---

## **STEP 3: Delete or Stop the RDS Instance**
- If you want to keep the data, create a **Final Snapshot** before deleting.

**How to delete:**
1. Go to **AWS Console** → **RDS**.  
2. Select the DB instance used (e.g., `monitoringdb`).  
3. Click **Actions** → **Delete**.  
4. Select **Create final snapshot** if you want to keep the data.  
5. Choose **Retain automated backups** or uncheck it if not needed.  
6. Type `delete me` in the confirmation box.  
7. Click **Delete**.  
    ![cleanup](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/6.clean/6.2.1.png)  
    ![cleanup](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/6.clean/6.2.2.png)  

> 📌 **Note:** If you only want to pause it for later testing, choose **Stop** instead of **Delete**.

---

## **STEP 4: Delete Snapshots if No Longer Needed**
1. In **RDS**, go to **Snapshots**.  
2. Tick the snapshot you don’t need.  
3. Click **Actions** → **Delete snapshot** → **Delete**.  
    ![cleanup](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/6.clean/6.3.1.png)  
    ![cleanup](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/6.clean/6.3.2.png)  

> 📌 **Reason:** Snapshots take up S3 storage space and incur monthly charges.

---

## **STEP 5: Delete Custom Security Groups / Parameter Groups**
**Security Group**  
1. Go to **EC2** → **Security Groups**.  
2. Select the security group created just for the workshop.  
3. Click **Actions** → **Delete security group**.  
    ![cleanup](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/6.clean/6.4.1.png)  

**Parameter Group**  
1. Go to **RDS** → **Parameter groups**.  
2. Select the custom parameter group.  
3. Click **Delete**.  

> 📌 **Reason:** If no longer in use, deleting them keeps things tidy and avoids confusion.

---

## **STEP 6: Check Billing**
1. Go to the **Billing Dashboard** in the **AWS Console**.  
2. Under **Bills** → **Current month**, check to ensure no services are incurring charges.  
3. Check **Cost Explorer** to ensure no resources are running in the background.
