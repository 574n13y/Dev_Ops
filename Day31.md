# Day 31

1. **Linux**: Explain `df -h` and `du` commands for disk usage.
   - **`df -h` (Disk Free):**  
  Displays the amount of disk space available on file systems. The `-h` flag makes the output human-readable (e.g., shows sizes in MB or GB).  
    Example:  
     ```bash
     df -h
     ```
  Output shows details like file system name, size, used space, available space, and mount points.

   - **`du` (Disk Usage):**  
  Shows the disk usage of files and directories. Use `-h` for human-readable format.  
  Example:  
     ```bash
     du -h /path/to/directory
     ```
  Output lists the size of each file and subdirectory under the specified path.

 
2. **Networking**: Describe NAT. Why is it useful?
   - **NAT (Network Address Translation):**  
  NAT allows private IP addresses within a local network to communicate with external networks (like the internet) by translating them into a public IP address.

   - **Why is it useful?**
    - **IP Conservation**: Reduces the need for a large number of public IP addresses.
    - **Security**: Hides internal network details from external networks.
    - **Connectivity**: Enables devices in private networks to access the internet while retaining privacy.

 
3. **Cloud Computing**: Explain the purpose of CloudWatch in AWS.
   - **AWS CloudWatch**:  
  A monitoring and observability service that provides actionable insights for AWS resources and applications.

   - **Key Features:**
    - **Metrics Monitoring**: Tracks resource utilization like CPU, memory, and disk usage.
    - **Logs Management**: Aggregates and analyzes application and system logs.
    - **Alarms**: Sends notifications or triggers actions when thresholds are breached.
    - **Dashboards**: Visualizes metrics for quick analysis.

   - **Use Case:** Monitor an EC2 instance's CPU usage and trigger an auto-scaling action when the usage exceeds a threshold.

   
4. **DevOps**: Describe the importance of code reviews.
   - **Why are code reviews important?**
    - **Error Detection**: Identifies bugs and issues early in development.
    - **Knowledge Sharing**: Promotes collaboration and learning among team members.
    - **Code Quality**: Ensures adherence to coding standards and best practices.
    - **Maintainability**: Encourages clean, readable, and maintainable code.
    - **Security**: Helps identify potential vulnerabilities.

  
5. **Tools & Technology**: Write a Terraform script to create an S3 bucket.
   
6. **Scenario**: How would you monitor application performance in AWS?
   

