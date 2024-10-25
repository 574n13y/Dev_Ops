🔸 AWS Question:
How can you test your backups in AWS to ensure they are reliable and usable in case of failure?
- To test your **backups in AWS**, you can:
1. **Perform Restore Tests:** Periodically restore backups to a new instance (EC2, RDS, etc.) and verify the data integrity and application functionality.
2. **Automate Backup Testing:** Use scripts or AWS services (like AWS Backup or Lambda) to regularly perform automated restores and checks.
3. **Disaster Recovery Drills:** Conduct full-scale tests that simulate a failure scenario, ensuring that the backup can be restored within the required recovery time.


🔸 Linux Question:
How do you find and kill a running process in Linux using the terminal? What command would you use to identify a process and terminate it?
- To find and kill a running process:
1. **Identify the Process:**
   ```bash
   ps aux | grep <process_name>
   ```
   or use `pgrep <process_name>` to get the process ID (PID).
2. **Kill the Process:**
   ```bash
   kill <PID>
   ```
   or use `kill -9 <PID>` to forcefully terminate it.


🔸 Networking Question:
What is the difference between TCP and UDP? Can you provide scenarios where each is preferred?
- **TCP (Transmission Control Protocol):** Connection-oriented, reliable, and ensures data is received in order. Preferred for scenarios where accuracy and data integrity are critical (e.g., web browsing, file transfers, emails).
- **UDP (User Datagram Protocol):** Connectionless, faster, and does not guarantee delivery. Suitable for scenarios where speed is more critical than reliability (e.g., online gaming, video streaming, VoIP).

🔸 DevOps Question:
How do you ensure that your infrastructure is provisioned consistently across multiple environments (e.g., dev, staging, prod) using Infrastructure as Code (IaC)?
- To ensure consistent infrastructure provisioning across multiple environments using **Infrastructure as Code (IaC)**:
1. **Use IaC Tools:** Utilize tools like Terraform, AWS CloudFormation, or Ansible to define infrastructure as code. This ensures that the same configuration is used across all environments.
2. **Version Control:** Store IaC templates in a version-controlled repository (like Git) to track changes and maintain consistency.
3. **Environment-Specific Variables:** Define environment-specific variables (e.g., dev, staging, prod) to customize configurations without altering the core infrastructure code.
4. **Automated Pipelines:** Integrate IaC scripts into CI/CD pipelines to automatically provision infrastructure in a repeatable and consistent manner.


