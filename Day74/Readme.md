# Day 74


1. **Linux**: Use `scp` for secure file transfers between servers.
   - `scp` (Secure Copy Protocol) is used to securely transfer files between local and remote systems.  

   **Example Usage:**  
   Copy a file from the local machine to a remote server:  
   ```bash
   scp file.txt username@remote_host:/remote/directory
   ```  

   Copy a file from a remote server to the local machine:  
   ```bash
   scp username@remote_host:/remote/file.txt /local/directory
   ```  

   Copy a directory recursively:  
   ```bash
   scp -r /local/directory username@remote_host:/remote/directory
   ```  


2. **Networking**: Explain the role of DNS in the internet.
   - DNS (Domain Name System) translates human-readable domain names (e.g., `www.example.com`) into IP addresses (e.g., `192.168.1.1`) that computers use to identify each other on the network.  

   **Key Roles of DNS:**
   - **Name Resolution:** Converts domain names to IP addresses.
   - **Load Balancing:** Directs traffic to multiple servers for redundancy and better performance.
   - **Caching:** Speeds up repeated queries by storing responses temporarily.
   - **Domain Aliases:** Links multiple domain names to a single IP address.


3. **Cloud Computing**: Discuss Amazon Athena and its usage.
   - Amazon Athena is a serverless interactive query service that allows you to analyze data in Amazon S3 using standard SQL.  

   **Key Features:**
   - **Serverless:** No infrastructure to manage.
   - **Integration with S3:** Queries directly on S3 data without moving it.
   - **Pay-per-Query:** Billed based on the amount of data scanned.
   - **Supports Multiple Formats:** Works with formats like CSV, JSON, Parquet, and ORC.

   **Use Cases:**
   - Data analysis and reporting.
   - Log analysis (e.g., CloudTrail logs).
   - Ad hoc queries on large datasets.


4. **DevOps**: Define observability and how it differs from monitoring.
   - **Observability** is the ability to understand the internal state of a system based on the data it produces (logs, metrics, and traces). It focuses on proactively identifying and resolving issues.  

   - **Monitoring**, on the other hand, is the process of collecting and analyzing system data to detect known issues and anomalies.  

   - **Differences:**
     | Aspect         | Observability                      | Monitoring                          |
     |----------------|------------------------------------|-------------------------------------|
     | Focus          | Proactive insights and debugging  | Reactive issue detection           |
     | Data Types     | Logs, metrics, traces             | Metrics and alerts                 |
     | Scope          | Unknown-unknowns                  | Known-unknowns                     |
     | Tools          | OpenTelemetry, Jaeger, Grafana    | Prometheus, Nagios, CloudWatch     |


5. **Tools & Technology**: Use Athena to query S3 data.
   * **Steps to Query Data Using Athena:**  
    
    1. **Prepare Your Data:**  
   Upload data to an S3 bucket (e.g., `s3://my-bucket/logs/`).  
    
    2. **Set Up a Table in Athena:**  
    - Go to the Athena console and choose the query editor.
    - Define a table with the schema of your data. Example:  
       ```sql
       CREATE EXTERNAL TABLE IF NOT EXISTS my_logs (
           log_time string,
           log_level string,
           message string
       )
       ROW FORMAT SERDE 'org.apache.hadoop.hive.serde2.lazy.LazySimpleSerDe'
       WITH SERDEPROPERTIES (
           'serialization.format' = '1'
       )
       LOCATION 's3://my-bucket/logs/'
       TBLPROPERTIES ('has_encrypted_data'='false');
       ```  
    
    3. **Run Queries:**  
       Use SQL to query the data:  
       ```sql
       SELECT log_level, COUNT(*) 
       FROM my_logs 
       GROUP BY log_level;
       ```  
    
    4. **Analyze Results:**  
       View query results in the Athena query editor or export them.


6. **Scenario**: You need a serverless solution to query stored data. How would you approach it?
   * To query data stored in S3:  
    
    1. **Use Amazon Athena:**  
    - Upload your data in supported formats (e.g., CSV, JSON, Parquet) to S3.
    - Set up schemas and tables in Athena for the data.
    - Use SQL to perform ad hoc analysis without managing infrastructure.
    
    2. **Enable Partitioning for Efficiency:**  
   Organize your data in S3 using folder structures (e.g., by date) for partitioned queries to reduce the amount of data scanned.  
    
    3. **Optimize Data Storage:**  
   Convert large datasets to efficient formats like Parquet or ORC to minimize query costs and improve performance.
    
    4. **Integrate with BI Tools:**  
   Use tools like QuickSight to visualize Athena query results for stakeholders.  

   * This approach provides a fully serverless, scalable, and cost-effective solution for querying large datasets.

