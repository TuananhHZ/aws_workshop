---
title : "Create an RDS Database for Monitoring"
date: 2025-08-07
weight : 1 
chapter : false
pre : " <b> 1.1 </b> "
---

## Step 1: Create an RDS Database for Monitoring



1. Go to [AWS Management Console](https://aws.amazon.com/console/) → **Services** → **RDS**.  
   ![RDS](/images/1.monitoring/1.1/1.1.1.png)


2. Click **Create Database** to start creating a new database instance.
    ![RDS](/images/1.monitoring/1.1/1.1.2.png)


3. **Choose Engine**:
   - Select **MySQL** or **PostgreSQL** depending on your needs.
    ![RDS](/images/1.monitoring/1.1/1.1.3.png)

   - **Template**: Select **Free Tier** to avoid charges (applicable if you are new to AWS).
    ![RDS](/images/1.monitoring/1.1/1.1.4.png)

4. **Fill in basic details**:
   - **DB Name (DB instance identifier)**: `monitoringdb`  
   - **Username**: e.g., `admin`  
   - **Password**: Enter, remember, and securely store for later use.
    ![RDS](/images/1.monitoring/1.1/1.1.5.png)


5. **Enable advanced monitoring options** (found under **Advanced settings**):
   - **Enable Enhanced Monitoring**  
   - **Enable Performance Insights**  
   - **Enable CloudWatch Logs exports** (select `error` and `slowquery`)
   ![RDS](/images/1.monitoring/1.1/1.1.6.png)

6. Click **Create Database** for AWS to start provisioning.  
    ![RDS](/images/1.monitoring/1.1/1.1.7.png)


   - The status will be **Creating**, and once it changes to **Available**, the server is ready to use.
   ![RDS](/images/1.monitoring/1.1/1.1.8.png)
