# Day 52

1. **Linux**: Use `chown` to change file and directory ownership.
   - The `chown` command changes the **ownership** of files or directories in Linux.
   - Ownership has two parts:
    - **User**: The owner of the file.
    - **Group**: A group of users that can access the file.

   #### Syntax:
        ```bash
        chown [OPTIONS] USER[:GROUP] FILE
        ```

   #### Examples:
   - Change the owner of a file:
     ```bash
     chown john file.txt
     ```
   - Change the owner and group:
     ```bash
     chown john:developers file.txt
     ```
   - Change ownership recursively (e.g., for directories):
     ```bash
     chown -R john:developers /path/to/directory
     ```


2. **Networking**: Define MTU (Maximum Transmission Unit) and its effect on networks.
   - **MTU** is the largest size of a packet that can be transmitted over a network without fragmentation.
   
   - Default MTU sizes:
    - Ethernet: 1500 bytes.
    - Jumbo frames: Up to 9000 bytes.
   
   - **Impact of MTU**:
    - Larger MTU improves efficiency by reducing the number of packets.
    - Smaller MTU can reduce latency but increases overhead.
    - Mismatched MTU settings may cause packet loss or fragmentation.

   #### Use Case:
    - MTU tuning is essential for applications that transfer large files or stream video to avoid performance degradation.


3. **Cloud Computing**: Discuss AWS CloudWatch and its monitoring capabilities.
   - **AWS CloudWatch** is a monitoring service for AWS resources and applications.
   - **Capabilities**:
    - Monitor metrics like CPU usage, memory, and disk utilization.
    - Collect and analyze logs using CloudWatch Logs.
    - Set alarms to notify users of thresholds or anomalies.
    - Create dashboards for real-time monitoring.
    - Use insights for troubleshooting and debugging.

   #### Use Case:
    - Monitor an EC2 instance's CPU and memory usage.
    - Set up alarms to detect when CPU usage exceeds 80%.


4. **DevOps**: Explain blue-green deployment and its advantages.
   - **Blue-Green Deployment** involves maintaining two environments:
   - **Blue**: The current production environment.
   - **Green**: The environment for deploying the new version.
   - During deployment, traffic is switched from Blue to Green.

   #### Advantages:
    - **Zero Downtime**: Traffic is seamlessly routed to the new version.
    - **Rollback Capability**: If issues arise, traffic can revert to the Blue environment.
    - **Testing in Production**: Green environment can be tested with real traffic before full switch-over.


5. **Tools & Technology**: Set up a monitoring dashboard in CloudWatch for CPU and memory.
    1. **Navigate to CloudWatch** in the AWS Management Console.
    2. **Create a Dashboard**:
    - Go to the **Dashboards** section.
    - Click **Create Dashboard**.
    - Name the dashboard.
    3. **Add Widgets**:
    - Select the widget type (e.g., Line Graph).
    - Choose the metrics:
    * CPU Utilization: `AWS/EC2 -> InstanceId -> CPUUtilization`.
    * Memory Utilization: Use **CloudWatch Agent** to collect memory metrics.
    4. **Save the Dashboard**:
    - Customize the layout and save changes.
    - Set alarms for thresholds like 80% CPU usage.


6. **Scenario**: Your application needs performance monitoring. How would you set it up?
    1. **Enable Monitoring**:
    - Use AWS CloudWatch to track metrics like CPU, memory, disk I/O, and network usage.
    - Install the **CloudWatch Agent** for in-depth metrics like memory utilization and disk space.
    2. **Create Alarms**:
    - Set alarms for high CPU or memory usage.
    - Example: Notify via SNS when CPU usage exceeds 80%.
    3. **Centralized Logs**:
    - Use **CloudWatch Logs** to collect application and system logs.
    4. **Visualization**:
    - Create dashboards to monitor real-time performance.
    - Add widgets for key metrics and alarms.
    5. **Scaling**:
    - Use CloudWatch alarms to trigger **Auto Scaling** for handling high traffic.


   
