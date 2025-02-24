# Day82 


1. **Linux**: Use `scp` to securely transfer files between remote systems.
   - `scp` (Secure Copy) is used to securely transfer files between local and remote systems over SSH.

   **Example Commands:**
   - Copy a file from local to remote:
     ```sh
     scp myfile.txt user@remote:/home/user/
     ```
   - Copy a file from remote to local:
     ```sh
     scp user@remote:/home/user/myfile.txt .
     ```
   - Copy an entire directory:
     ```sh
     scp -r myfolder user@remote:/home/user/
     ```


2. **Networking**: Explain NAT gateways and instances and their role in VPCs.
   - Both NAT Gateways and NAT Instances allow instances in **private subnets** to access the internet **without** exposing them to inbound connections.

   | Feature            | NAT Gateway                   | NAT Instance                  |
   |-------------------|-----------------------------|------------------------------|
   | **Managed by AWS** | Yes                          | No (user-managed EC2 instance) |
   | **High Availability** | Multi-AZ support            | No (single point of failure) |
   | **Scaling**        | Scales automatically        | Needs manual scaling         |
   | **Performance**    | Higher performance          | Limited by EC2 type          |
   | **Use Case**      | Recommended for production  | Used in cost-sensitive cases |

   **✅ Best Practice**: Use **NAT Gateway** for better availability and performance.


3. **Cloud Computing**: Describe Amazon CloudWatch Alarms.
   - CloudWatch Alarms **monitor AWS metrics** and take automated actions based on thresholds.

   **Key Features:**
   - **Trigger Actions** (send notifications, auto-scale, stop instances).
   - **Threshold-Based Alerts** (CPU utilization, network traffic, memory usage).
   - **Multiple States**:
    - **OK** – Metric is within the normal range.
    - **ALARM** – Metric exceeds threshold.
    - **INSUFFICIENT DATA** – No data is available.

   **Example Use Cases:**
    - Alert when **EC2 CPU usage** exceeds 80%.
    - Trigger an **Auto Scaling policy** when request count increases.
    - Stop an idle EC2 instance to save costs.


4. **DevOps**: What is synthetic monitoring, and how does it help in proactive monitoring?
   - **Synthetic monitoring** (active monitoring) simulates user interactions to detect issues **before** real users are affected.

   **How It Works:**
    - Uses **scripts or agents** to test API endpoints, websites, or applications.
    - Runs periodic checks from **multiple locations**.
    - Detects **downtime, performance issues, slow pages**.

   **Benefits:**
    ✅ Identifies issues before users experience them.  
    ✅ Helps in **SLA (Service Level Agreement) compliance**.  
    ✅ Monitors **third-party services (APIs, CDNs, DBs)**.  

   **Examples of Synthetic Monitoring Tools:**
    - **AWS CloudWatch Synthetics**
    - **New Relic Synthetic Monitoring**
    - **Datadog Synthetic Tests**


5. **Tools & Technology**: Create a CloudWatch Alarm to monitor EC2 CPU usage.
   - **Terraform Code to Set Up CloudWatch Alarm**
     ```hcl
     resource "aws_cloudwatch_metric_alarm" "cpu_alarm" {
       alarm_name          = "high-cpu-usage"
       comparison_operator = "GreaterThanThreshold"
       evaluation_periods  = 2
       metric_name        = "CPUUtilization"
       namespace         = "AWS/EC2"
       period           = 60
       statistic        = "Average"
       threshold        = 80
       alarm_description = "Alarm when CPU exceeds 80%"
       alarm_actions     = [aws_sns_topic.alert_topic.arn]
     
        dimensions = {
          InstanceId = "i-1234567890abcdef0"
       }
      }

      resource "aws_sns_topic" "alert_topic" {
        name = "ec2-alert-topic"
      }

      resource "aws_sns_topic_subscription" "email_alert" {
        topic_arn = aws_sns_topic.alert_topic.arn
        protocol  = "email"
        endpoint  = "your-email@example.com"
     }
     ```

   ✅ **When CPU usage exceeds 80% for 2 minutes, an alert is sent to an SNS topic.**


6. **Scenario**: You want to receive alerts when server utilization crosses a threshold. How would you set this up?
   - **Steps to Set Up CloudWatch Alarms in AWS Console**
    1. **Go to AWS CloudWatch → Alarms → Create Alarm**.
    
    2. **Select Metric**: EC2 → Per-Instance Metrics → CPUUtilization.
    
    3. **Set Conditions**:
    - Threshold: **Greater than 80%**
    - Period: **1 minute**
    
    4. **Set Actions**:
    - **SNS Notification** → Send an email or trigger an Auto Scaling action.
    
    5. **Review and Create Alarm**.

    ✅ **Now, you will get alerts when server utilization crosses the threshold!** 🚀  


 
