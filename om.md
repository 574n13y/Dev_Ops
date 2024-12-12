# Day 37

1. **Linux**: Learn to use rsync to synchronize files.
#### **Key Points**
- **What is `rsync`?**
  - A Linux command-line utility for efficiently transferring and synchronizing files across directories or systems.
  - Supports incremental file transfers, ensuring only modified files are copied.

#### **Basic Commands**
- Sync files locally:
  ```bash
  rsync -av source_directory/ destination_directory/
  ```
- Sync files over SSH:
  ```bash
  rsync -av -e ssh source_directory/ user@remote_host:/path/to/destination/
  ```
- Perform a dry run:
  ```bash
  rsync -av --dry-run source_directory/ destination_directory/
  ```
- Exclude files or directories:
  ```bash
  rsync -av --exclude 'file_or_dir_name' source_directory/ destination_directory/
  ```

#### **Benefits**
- Efficient data transfer.
- Built-in compression with the `-z` flag.
- Useful for backups and migrations.

   
2. **Networking**: Explain the concept of load balancing and its benefits.
#### **Concept**
- **Load Balancing** is the process of distributing incoming network traffic across multiple servers to ensure no single server is overwhelmed.

#### **Benefits**
- **Scalability**: Handles increased traffic by distributing load across multiple servers.
- **High Availability**: Ensures system uptime by redirecting traffic from failing servers.
- **Improved Performance**: Reduces latency by routing requests to the nearest or least-loaded server.
- **Fault Tolerance**: Automatically redirects traffic when a server is down.

#### **Load Balancing Algorithms**
- **Round Robin**: Distributes traffic sequentially.
- **Least Connections**: Directs traffic to the server with the fewest active connections.
- **IP Hash**: Routes traffic based on the client’s IP address.
- **Weighted Algorithms**: Assigns weights to servers based on their capacity.


3. **Cloud Computing**: Describe Amazon RDS and its key features.
#### **What is Amazon RDS?**
- **Amazon Relational Database Service (RDS)** is a managed database service that simplifies the setup, operation, and scaling of relational databases in the cloud.

#### **Key Features**
- **Support for Popular Engines**: MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, and Amazon Aurora.
- **Automated Maintenance**: Handles database patches and backups.
- **High Availability**: Supports multi-AZ deployments for failover.
- **Scalability**: Easy to scale compute and storage resources.
- **Security**: Integrated with AWS IAM, KMS, and VPC for robust security.

#### **Use Cases**
- E-commerce platforms.
- Analytics and reporting.
- Scalable web applications.


4. **DevOps**: What are secrets management and environment variables?

5. **Tools & Technology**: Install Vault for secret management and set up a basic secret.

6. **Scenario**: Your team needs to secure application credentials. How would you handle it?


