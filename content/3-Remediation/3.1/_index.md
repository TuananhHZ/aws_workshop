---
title : "Create a Lambda Function for Remediation"
date: 2025-08-07
weight : 1
chapter : false
pre : " <b> 3.1. </b> "
---



### Step 7 – Create a Lambda Function for Remediation

#### **Objective**  
Create a Lambda function to automatically reboot the RDS instance when needed.

---

#### **Open Lambda**
- Go to **AWS Management Console** → search for **Lambda** → **Create function**.  
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.1.png)  
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.2.png)

---

#### **Initial Configuration**
1. Select **Author from scratch**.  
2. **Function name**: `rds-auto-reboot` *(or any name you prefer)*.  
3. **Runtime**: `Python 3.12`.  
4. **Permissions**:  
   - Choose **Create a new role with basic Lambda permissions**.  
     ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.3.png)  

> **Note**: After creating the function, go to **IAM → Roles** and **add** the `AmazonRDSFullAccess` policy to this role (so Lambda can reboot the RDS instance).

   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.4.png)  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.5.png)  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.6.png)  
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.7.png)  

---

#### **Insert the Processing Code**
In the **Code editor** section of Lambda, paste the following code:
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
- Click Deploy to save the code.
- You can test it by creating a mock event to ensure the Lambda runs correctly.
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.10.png)
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.11.png)
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.1/3.1.12.png)