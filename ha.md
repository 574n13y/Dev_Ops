# Day 58


1. **Linux**: Use `cron` to automate a daily backup.
   - The `cron` utility in Linux is used to schedule tasks. To automate a daily backup, follow these steps:
 
    1. **Create a Backup Script**:
   ```bash
   #!/bin/bash
   tar -czf /backup/my_backup_$(date +%Y-%m-%d).tar.gz /path/to/files
   ```
   Save this script as `backup.sh` and make it executable:
   ```bash
   chmod +x backup.sh
   ```
  
    2. **Schedule the Script Using `cron`**:
   Open the `crontab` editor:
   ```bash
   crontab -e
   ```
   Add the following line to schedule the backup at 2 AM daily:
   ```bash
   0 2 * * * /path/to/backup.sh
   ```
   Save and exit. The task will now run daily at the specified time.


2. **Networking**: Describe NAT Gateway and its use cases in cloud environments.
   - A **NAT Gateway (Network Address Translation Gateway)** allows instances in a private subnet to access the internet while preventing incoming traffic from the internet.

   **Use Cases**:
    1. **Private Subnet Internet Access**: Instances in private subnets can download updates or connect to external APIs.
    2. **Secure Architectures**: Protects private instances from direct exposure to the internet.
    3. **Cost Efficiency**: A managed NAT Gateway is easier to maintain compared to custom NAT instances.


3. **Cloud Computing**: Explain AWS CloudFormation and its advantages.

4. **DevOps**: Compare manual provisioning vs. IaC.

5. **Tools & Technology**: Deploy a CloudFormation stack to create a VPC.

6. **Scenario**: Your infrastructure needs a repeatable deployment setup. How would you achieve this?

