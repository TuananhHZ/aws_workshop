---
title : "Monitor Real-Time Metrics and Performance Insights"
date: 2025-08-07
weight : 3
chapter : false
pre : " <b> 1.3 </b> "
---



## Step 3: Monitor Real-Time Metrics and Performance Insights
### View real-time metrics on CloudWatch
1. Go to **AWS Console** → **CloudWatch** → **Metrics**. 
2. Select **Browse** → **RDS** → **Per-Database Metrics**.
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.8.png)

3. Select **DBInstanceIdentifier** `monitoringdb-1`.
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.9.png)

4. Check the important metrics:
- **CPUUtilization**
- **FreeableMemory**
- **ReadIOPS, WriteIOPS**
- **DatabaseConnections**
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.10.png)

5. Click **Add to dashboard** if you want to display it directly on the dashboard.
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/1.monitoring/1.3/1.3.11.png)


