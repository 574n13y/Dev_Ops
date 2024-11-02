# Day 15

🔸 AWS Question:
How does Amazon RDS handle automated backups, and how can you restore a database to a specific point in time?
- Amazon RDS automatically creates daily snapshots and transaction logs to enable point-in-time recovery (PITR) for databases. Automated backups are retained for a set period (typically 7 to 35 days) and occur within a specified backup window. RDS stores these backups in Amazon S3, ensuring durability.
- To restore to a specific point in time, you can initiate a new RDS instance using the backup from your desired time within the retention period. RDS will replay transaction logs up to the specified second, making it possible to recover data to an exact point. The restored instance is a separate database, which helps you avoid overwriting the existing one.


🔸 Linux Question:
How would you create a cron job to run a script every Monday at 3:00 AM.
- To schedule a cron job for every Monday at 3:00 AM, open the crontab file by running:
```bash
crontab -e
```
Add this line to the file:
```bash
0 3 * * 1 /path/to/your/script.sh
```

Explanation:
  - `0 3 * * 1` specifies the timing:
  - `0` - Minute (0th minute of the hour)
  - `3` - Hour (3 AM)
  - `* *` - Every day and every month
  - `1` - Monday
  - `/path/to/your/script.sh` is the path to the script you want to run.


🔸 Networking Question:
What is ARP (Address Resolution Protocol), and how does it help devices on a local network communicate with each other?
- ARP, or Address Resolution Protocol, is used to map a device’s IP address to its MAC (Media Access Control) address on a local network. When a device needs to communicate with another on the same subnet, it sends an ARP request, essentially asking, "Who has this IP address?" The device with that IP responds with its MAC address, enabling direct communication over the Ethernet network.

- This mapping is crucial for local communication because while IP addresses facilitate identification within a network layer, MAC addresses are essential for data-link layer interactions on a physical network. Devices maintain an ARP cache, so they don’t have to repeatedly send requests for known addresses.

🔸 DevOps Question:
How do configuration management tools like Ansible or Chef work in a DevOps environment, and how do they help ensure consistency across servers?

