# CLOUD-MONITORING-AND-ALERTS

COMPANY : CODTECH IT SOLUTIONS

NAME : BHARATH P

INTERN ID : CT08VOM

DOMAIN : CLOUD COMPUTING

DURATION : 4 WEEKS

MENTOR : NEELA SANTOSH


____________________________________________________________________________________________________________
DESCRIPTION:

## Cloud Monitoring and Alerts with AWS CloudWatch

This guide walks you through setting up **monitoring and alerts** for a cloud-based application using **AWS CloudWatch**.
By the end, you’ll have a **dashboard showcasing key metrics** and **configured alerts** for your application.

---

## **Prerequisites**
1. An **AWS account** with access to CloudWatch.
2. Resources (e.g., EC2 instances, Lambda functions, RDS databases) deployed in AWS.

---

## **Steps to Set Up Monitoring and Alerts**

### **1. Enable CloudWatch Monitoring**
Ensure your AWS resources are sending metrics to CloudWatch:
- For **EC2 instances**, enable **Detailed Monitoring** in the EC2 dashboard.
- For **Lambda functions**, metrics are automatically sent to CloudWatch.
- For **RDS databases**, ensure monitoring is enabled in the RDS dashboard.


### **2. Create a CloudWatch Dashboard**
1. Go to the **CloudWatch** console in the AWS Management Console.
2. Navigate to **Dashboards** and click **Create Dashboard**.
3. Name your dashboard (e.g., `Bharath-AWS`).
4. Add widgets to visualize metrics.
5. Repeat the process to add more widgets for other metrics.
6. Arrange the widgets on the dashboard for better visibility.


### **3. Set Up CloudWatch Alarms**
1. In the CloudWatch console, go to **Alarms** and click **Create Alarm**.
2. Choose a metric:
   - Click **Select Metric**.
   - Choose the namespace (e.g., EC2, Lambda, RDS).
   - Select the metric (e.g., CPUUtilization for EC2, Errors for Lambda).
3. Set the alarm conditions:
   - Define the threshold (e.g., CPU > 80% for 5 minutes).
   - Choose the statistic (e.g., Average, Maximum).
   - Set the period (e.g., 1 minute, 5 minutes).
4. Configure actions:
   - Click **Add Notification**.
   - Choose an existing **SNS Topic** or create a new one.
   - Enter your email address to receive notifications.
   - Confirm the subscription by clicking the link in the confirmation email.
5. Set additional actions (optional):
   - Trigger an Auto Scaling policy (e.g., scale out if CPU is high).
   - Trigger a Lambda function (e.g., to remediate the issue).
6. Name your alarm (e.g., `High-CPU-Alarm`) and click **Create Alarm**.


### **4. Test Your Setup**
- Simulate high CPU usage or errors on your application.
- Verify that the metrics appear on your CloudWatch dashboard.
- Check if the alarm triggers and you receive a notification via email.

---

## **Deliverables**
1. A **CloudWatch Dashboard** with widgets displaying key metrics (e.g., CPU, memory, errors).
2. Configured **CloudWatch Alarms** with notifications sent to your email or other channels (e.g., Slack via SNS).

---

## **Example Dashboard and Alarms**
### **Dashboard Widgets**:
- **EC2 Metrics**:
  - CPU Utilization (Line Chart)
  - Network In/Out (Stacked Area Chart)
- **Lambda Metrics**:
  - Invocations (Number Widget)
  - Errors (Line Chart)
- **RDS Metrics**:
  - DatabaseConnections (Line Chart)
  - FreeStorageSpace (Number Widget)

### **Alarms**:
- **High CPU Alarm**:
  - Metric: EC2 CPUUtilization
  - Condition: > 80% for 5 minutes
  - Action: Send email notification
- **Lambda Error Alarm**:
  - Metric: Lambda Errors
  - Condition: > 0 for 1 minute
  - Action: Send email notification
---

## **Output:**

### Dashboard
