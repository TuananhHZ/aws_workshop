---
title : "Create a High CPU Alert "
date: 2025-08-07
weight : 2
chapter : false
pre : " <b> 2.1 </b> "
---



## Step 5 – Create a High CPU Alert

**Objective:** Alert when RDS CPU usage > 80% for 5 consecutive minutes.

---

### 1. Open CloudWatch
1. In **AWS Console**, search for **CloudWatch**.
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.1.png)
2. On the left menu, select **Alarms** → **Create alarm**.
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.1.png)

---

### 2. Select Metric
1. Click **Select metric**.
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.2.png)

2. Navigate to **RDS** → **Per-Database Metrics**.
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.3.png)
  
3. Select your **DB instance**.
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.4.png)

4. Find and choose **CPUUtilization** → click **Select metric**.
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.5.png)

---

### 3. Configure Alarm Conditions
- **Statistic:** Average  
- **Period:** 1 minute *(or 5 minutes to reduce alert frequency)*  
- **Threshold type:** Static  
- **Condition:** Greater than  
- **Threshold value:** `80`  
- **Evaluation period:** Select **for 5 consecutive periods** to require 5 minutes of sustained CPU > 80%.
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.6.png)


---

### 4. Configure Actions
1. Under **In alarm**, choose **Send a notification to an SNS topic**.
2. If you don't have a topic yet, click **Create new topic**:
   - **Name:** `rds-cpu-alert`
   - **Subscription:** Email → enter the email to receive alerts.
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.7.png)

3. AWS will send a confirmation email → **click the Confirm link** to activate the alert subscription.
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.8.png)

---

### 5. Name & Create Alarm
1. **Name:** `RDS-High-CPU-Alarm`
2. Click **Review** → **Create alarm**.
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.9.png)
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.1/2.1.10.png)


---
