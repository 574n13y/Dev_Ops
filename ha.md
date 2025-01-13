# Day 60


1. **Linux**: Use `top` to monitor system resources in real time.
* The `top` command in Linux allows you to monitor system resources and processes in real time. Here's how to use it:

- **Launch `top`**: Run `top` in your terminal.
- **Key Metrics**:
  - **CPU Usage**: Percentage of CPU used by processes.
  - **Memory Usage**: RAM consumption by the system and processes.
  - **Load Average**: System load over the last 1, 5, and 15 minutes.
  - **Processes**: Number of total, running, sleeping, and zombie processes.
- **Interactive Commands**:
  - `k`: Kill a process (enter the PID when prompted).
  - `r`: Change the priority (nice value) of a process.
  - `q`: Quit the `top` command.
  - `h`: View help for additional commands.


2. **Networking**: Define network packets and their components.
* A **network packet** is a formatted unit of data carried across a network. Its components include:

- **Header**:
  - **Source Address**: The IP address of the sender.
  - **Destination Address**: The IP address of the recipient.
  - **Protocol**: Specifies the protocol used (e.g., TCP, UDP).
  - **Sequence Number**: Identifies the order of the packet in a transmission.
  - **Checksum**: Ensures data integrity.
  
- **Payload**:
  - Contains the actual data being transmitted (e.g., part of a file, a message).
  
- **Trailer**:
  - Marks the end of the packet and may include error-checking data (e.g., cyclic redundancy check).


3. **Cloud Computing**: Describe EC2 Auto Scaling policies.
* EC2 Auto Scaling policies automatically manage the number of Amazon EC2 instances in a group based on application demand or predefined schedules. Key policies include:

1. **Target Tracking Scaling**:
   - Adjusts the number of instances to maintain a specified metric at a target value.
   - Example: Keeping CPU utilization at 50%.

2. **Step Scaling**:
   - Adds or removes instances based on metric thresholds that trigger step adjustments.
   - Example: Adding 2 instances if CPU utilization exceeds 70%.

3. **Scheduled Scaling**:
   - Scales the number of instances based on a predefined schedule.
   - Example: Increasing instance count during peak business hours.

4. **Predictive Scaling**:
   - Uses machine learning to predict future demand and scales capacity in advance.


4. **DevOps**: What are the best practices for secrets management?

5. **Tools & Technology**: Set up AWS Secrets Manager for storing API keys.

6. **Scenario**: Your app requires secure management of sensitive data. How would you handle it?


