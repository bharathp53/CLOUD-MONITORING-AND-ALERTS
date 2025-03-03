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

---

### **2. Create a CloudWatch Dashboard**
1. Go to the **CloudWatch** console in the AWS Management Console.
2. Navigate to **Dashboards** and click **Create Dashboard**.
3. Name your dashboard (e.g., `MyApp-Monitoring-Dashboard`).
4. Add widgets to visualize metrics:
   - Click **Add Widget**.
   - Choose a widget type (e.g., Line, Stacked Area, Number).
   - Select the metrics you want to monitor:
     - **EC2**: CPUUtilization, NetworkIn, NetworkOut, DiskReadOps, DiskWriteOps.
     - **Lambda**: Invocations, Errors, Duration, Throttles.
     - **RDS**: CPUUtilization, DatabaseConnections, FreeStorageSpace.
   - Customize the time range (e.g., last 1 hour, last 24 hours).
5. Repeat the process to add more widgets for other metrics.
6. Arrange the widgets on the dashboard for better visibility.

---

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

---

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

## **Optional: Advanced Features**
- **Logs Monitoring**:
  - Use **CloudWatch Logs** to monitor application logs.
  - Set up log-based metrics and alarms.
- **Custom Metrics**:
  - Use the CloudWatch API to send custom metrics from your application.
- **Anomaly Detection**:
  - Enable anomaly detection for metrics to identify unusual behavior.

---

For more details, refer to the [AWS CloudWatch Documentation](https://docs.aws.amazon.com/cloudwatch/).

---
