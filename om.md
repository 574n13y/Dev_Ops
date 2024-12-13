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

3. **Cloud Computing**: Describe the differences between Amazon S3 and EBS.

4. **DevOps**: What’s a microservices architecture, and why is it used?

5. **Tools & Technology**: Set up Docker Compose for a multi-container application.

6. **Scenario**: How would you deploy a microservices application locally?

