---
title : "Create CloudWatch Dashboard"
date: 2025-08-07
weight : 1
chapter : false
pre : " <b> 4.1 </b> "
---



### Step 9: Create CloudWatch Dashboard  
**Objective**: Have a visual dashboard to monitor the **RDS database** status and key metrics.

---

#### 1. Open CloudWatch Dashboards  
- Log in to the **AWS Management Console**.  
- Search for **CloudWatch** in the search bar and open it.  
- In the left menu, select **Dashboards**.  
- Click **Create dashboard**.  
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/4.dashboard/4.1/4.1.1.png)

---

#### 2. Name the Dashboard  
- Enter a name, for example: `RDS-Monitoring-Dashboard`.  
- Click **Create dashboard**.  
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/4.dashboard/4.1/4.1.2.png)

---

#### 3. Add Widgets  
##### **Widget 1: CPU Utilization**  
- Select **Line** (or **Number** if you prefer a realtime number display).  
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/4.dashboard/4.1/4.1.9.png)

- Click **Next**.  
- In **Browse**, select:  
  - `RDS → DB Instance → <database name>`  
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/4.dashboard/4.1/4.1.4.png)  
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/4.dashboard/4.1/4.1.5.png)  

  - **Metric**: `CPUUtilization`  
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/4.dashboard/4.1/4.1.6.png)  

- Click **Create widget**.  
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/4.dashboard/4.1/4.1.7.png)  
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/4.dashboard/4.1/4.1.8.png)  

+ Repeat the same steps for the following **Metrics**:  
  - **Metric**: `FreeableMemory`  
  - **Metric**: `ReadIOPS`  
  - **Metric**: `WriteIOPS`  
  - **Metric**: `DatabaseConnections`  

+ Arrange the **Metrics** appropriately:
  ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/4.dashboard/4.1/4.1.13.png)