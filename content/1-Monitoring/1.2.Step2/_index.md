---
title : "Enable and Check Amazon CloudWatch Logs "
date: 2025-08-07
weight : 2
chapter : false
pre : " <b> 1.2 </b> "
---

## Step 2: Enable and Check Amazon CloudWatch Logs

### 1. Check / Enable Log Export on RDS (if not already enabled)
- Go to **AWS Console** → **RDS** → **Databases** → select the instance (`monitoringdb`) → **Modify**.      
- Find the **Monitoring** or **Additional configuration** section (depending on the interface) → **Log exports** / **CloudWatch Logs exports**.  
- Tick the following:
  - **Error log**
  - **Slow query log** (or logs relevant to the engine: `error`, `slowquery`, `postgresql`, ...).  
- **Save / Apply changes** → may require **Reboot** if parameter changes need a restart.  
  
- **For MySQL**: you must enable `slow_query_log = 1` and set `long_query_time` in the **DB parameter group** so that slow query logs are exported.  
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.2/1.2.1.png)  
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.2/1.2.2.png)  
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.2/1.2.3.png)  
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.2/1.2.4.png)  

---

### 2. View Log Groups in CloudWatch
- **AWS Console** → **CloudWatch** → **Logs** → **Log groups**.  
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.1.png)  

### 3. Create a Metric Filter from Logs

1. In **CloudWatch** → **Logs**, select the log group  
2. Click **Create metric filter**.  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.2.png)  

3. Enter **Filter pattern**: `ERROR` → Next  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.3.png)  

### 4. Configure:

- **Metric namespace**: `RDSLogs` (example)  
- **Metric name**: `ErrorCount`  
- **Metric value**: `1`  

- Create the metric filter, then create an **Alarm** for the metric `RDSLogs / ErrorCount`  
- Click **Next**:  
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.4.png)  
- Click **Create metric filter**:   
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.5.png)  
- You will get:   
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.6.png)  

### 5. Quick Error Query
**Steps to perform**:

- Go to **CloudWatch** → **Logs Insights**.  
1. Select the log group.  
2. Enter the query to filter errors:  
```sql
fields @timestamp, @message
| filter @message like /ERROR/
| sort @timestamp desc
| limit 50
```
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.7.png)