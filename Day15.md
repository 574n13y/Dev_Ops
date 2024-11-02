# Day 15

🔸 AWS Question:
How does Amazon RDS handle automated backups, and how can you restore a database to a specific point in time?
- Amazon RDS automatically creates daily snapshots and transaction logs to enable point-in-time recovery (PITR) for databases. Automated backups are retained for a set period (typically 7 to 35 days) and occur within a specified backup window. RDS stores these backups in Amazon S3, ensuring durability.
- To restore to a specific point in time, you can initiate a new RDS instance using the backup from your desired time within the retention period. RDS will replay transaction logs up to the specified second, making it possible to recover data to an exact point. The restored instance is a separate database, which helps you avoid overwriting the existing one.


🔸 Linux Question:
How would you create a cron job to run a script every Monday at 3:00 AM.

🔸 Networking Question:
What is ARP (Address Resolution Protocol), and how does it help devices on a local network communicate with each other?

🔸 DevOps Question:
How do configuration management tools like Ansible or Chef work in a DevOps environment, and how do they help ensure consistency across servers?

