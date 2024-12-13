# Day 38

1. **Linux**: Work with `cron` to schedule recurring tasks.
#### **What is `cron`?**
`cron` is a Linux utility used to schedule tasks to run automatically at specified intervals.

#### **Key Steps**
    1. **Edit `crontab`**:
   Open the crontab editor:
   ```bash
   crontab -e
   ```
    2. **Add a Cron Job**:
   Syntax:
   ```
   * * * * * /path/to/script
   ```
   - **Fields**:
     - `Minute (0–59)`, `Hour (0–23)`, `Day of Month (1–31)`, `Month (1–12)`, `Day of Week (0–6)`
   - Example: Run a script daily at 2:00 AM:
     ```bash
     0 2 * * * /path/to/backup.sh
     ```

#### **Common Commands**
- **List Scheduled Tasks**:
  ```bash
  crontab -l
  ```
- **Remove Scheduled Tasks**:
  ```bash
  crontab -r
  ```

#### **Advanced Features**
- Redirect output:
  ```bash
  0 2 * * * /path/to/script.sh >> /path/to/logfile 2>&1
  ```


2. **Networking**: Explain the concept of latency and its impact on network performance.
#### **What is Latency?**
- Latency is the time taken for a data packet to travel from the source to the destination and back (round-trip time).
- Measured in milliseconds (ms).

#### **Impact on Network Performance**
- **High Latency**:
  - Causes delays in communication.
  - Degrades user experience in real-time applications (e.g., video calls, gaming).
- **Causes of High Latency**:
  - Network congestion.
  - Geographical distance.
  - Inefficient routing or hardware bottlenecks.

#### **Reducing Latency**
- Use a **Content Delivery Network (CDN)** to cache data closer to users.
- Optimize network routes and infrastructure.
- Use low-latency protocols (e.g., UDP for streaming).


3. **Cloud Computing**: Describe the differences between Amazon S3 and EBS.
| Feature                        | **Amazon S3**                                                                                  | **Amazon EBS**                                                                                       |
|--------------------------------|------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------|
| **Type**                       | Object storage                                                                                 | Block storage                                                                                       |
| **Purpose**                    | Store unstructured data like files, images, and backups.                                       | Attachable to EC2 instances for file systems, databases, or applications requiring low-latency I/O. |
| **Scalability**                | Infinitely scalable.                                                                           | Limited to the size of the volume (max 16 TiB).                                                     |
| **Data Access**                | Accessible over the internet via APIs.                                                        | Accessible only when attached to an EC2 instance.                                                  |
| **Use Case**                   | Backup, archival, static website hosting.                                                     | Persistent storage for running applications or databases.                                           |
| **Pricing**                    | Pay-per-use based on storage size and requests.                                               | Pay for provisioned storage size, regardless of usage.                                             |



4. **DevOps**: What’s a microservices architecture, and why is it used?

5. **Tools & Technology**: Set up Docker Compose for a multi-container application.

6. **Scenario**: How would you deploy a microservices application locally?

