---
title : "Create a rule to invoke Lambda when the alarm is triggered"
date: 2025-08-07
weight : 2
chapter : false
pre : " <b> 3.2. </b> "
---



## Step 8: Create a rule to invoke Lambda when the alarm is triggered

### 1. Open EventBridge
- Go to **AWS Management Console** → search for **EventBridge** → **Rules** → **Create rule**.
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.2/3.2.1.png)
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.2/3.2.2.png)
---

### 2. Rule information
- **Name**: `auto-reboot-on-highcpu-2` (or any name you want).
- **Event bus**: `default`.
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.2/3.2.3.png)
---

### 3. Select Event Source
- **AWS events or EventBridge partner events**.
- **Event source**: `AWS services`.
- **Service name**: `CloudWatch`.
- **Event type**: `CloudWatch Alarm State Change`.
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.2/3.2.5.png)
---

### 4. Filter the alarm to capture
In the **pattern** section, select the following condition:

```json
{
  "source": ["aws.cloudwatch"],
  "detail-type": ["CloudWatch Alarm State Change"],
  "detail": {
    "alarmName": ["HighCPUAlarm"],
    "state": {
      "value": ["ALARM"]
    }
  }
}
```
   ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.2/3.2.6.png)

## 5. Select Target
- **Target type**: `Lambda function`
- Select the **Lambda function** you just created (`rds-auto-reboot`)
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.2/3.2.7.png)
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.2/3.2.8.png)

## 6. Create Rule
- Click **Create** to complete.
    ![RDS](https://github.com/TuananhHZ/Aws_Whorkshop.git/images/3.remediation/3.2/3.2.9.png)

## 7. Result
- When the **alarm** is triggered, the **Lambda** will automatically **reboot the DB**.
