---
title : "Alerting Overview "
date: 2025-08-07
weight : 2
chapter : false
pre : " <b> 2. </b> "
---



### 1. What is Alerting?
- **Alerting** is the process of notifying administrators, DevOps engineers, or support teams when certain conditions, thresholds, or patterns are detected in a system’s metrics or logs.  
- It plays a critical role in maintaining **system reliability** and **service uptime** by enabling **quick detection** and **response to issues**.  

- Key objectives of alerting:  
  - Detect incidents early  
  - Minimize downtime  
  - Provide actionable notifications  
  - Avoid alert fatigue by ensuring alerts are relevant  

---

### 2. How Alerting Works
1. **Data Collection** – Metrics, logs, and traces are collected from various services (e.g., EC2, RDS, Lambda).  
2. **Condition Evaluation** – Rules or thresholds are applied to detect unusual events or performance degradation.  
3. **Alert Trigger** – If conditions are met, an alert is generated.  
4. **Notification Delivery** – Alerts are sent to channels such as email, Slack, SNS, PagerDuty, etc.    

---

### 3. Common Alert Types
- **Threshold-based alerts**: Triggered when a metric value crosses a predefined limit (e.g., CPU > 80%).  
- **Anomaly detection alerts**: Triggered when the system detects unusual patterns that differ from historical trends.  
- **Log pattern alerts**: Triggered when certain keywords or error patterns appear in logs.  

---

### 4. Best Practices
- Set thresholds based on **historical data** and **service SLAs**.  
- Use multiple severity levels (Info, Warning, Critical).  
- Group related alerts to avoid notification spam.  
- Regularly review and update alert rules.  

---

