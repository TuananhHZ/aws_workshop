---
title : "Create an Alert from Error Logs "
date: 2025-08-07
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---



## Step 6 – Create an Alert from Error Logs

**Objective:** Trigger an alert when the RDS log contains the word `"ERROR"` at least 2 times within 5 minutes.

---

### 1. Access CloudWatch Logs
- Open **AWS Console** → **CloudWatch** → **Logs** → **Log groups**.
- Locate the RDS log group.
- Click on the log group.  
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.1.png)

---

### 2. Create a Metric Filter
1. Click **Create metric filter**.
2. In **Filter pattern**, enter:
3. Click **Test pattern** to ensure it correctly filters logs containing `ERROR`.
4. Click **Next**.  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.2.png)  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.3.png)

---

### 3. Assign Metric Name
- **Metric name:** `ErrorCount`
- **Metric namespace:** `RDSLogs` (customizable).
- **Metric value:** `1`
- Click **Create filter**.  
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.4.png)  
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.5.png)  
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.6.png)

---

### 4. Create an Alarm for the Metric
1. Once the metric filter is created, click **Create alarm**.  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.2/2.2.1.png)

2. **Condition:** `ErrorCount > 1` within **5 minutes**.  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.2/2.2.2.png)

3. **Actions:** Send a notification via **SNS** (can use the same email topic from *Step 5*).  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.2/2.2.3.png)  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.2/2.2.4.png)  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/2.alerting/2.2/2.2.5.png)

---
