# Day 35

1. **Linux**: Use `find` to search for files. Experiment with different flags.
   - The `find` command is a powerful tool to search for files and directories in Linux.

     **Examples:**
   - **Find files by name**:
      ```bash
      find /path/to/search -name "filename"
      ```
   - **Find files by extension**:
      ```bash
      find /path/to/search -name "*.txt"
      ```
   - **Find files modified in the last 7 days**:
      ```bash
      find /path/to/search -type f -mtime -7
      ```
   - **Find files larger than 1MB**:
      ```bash
      find /path/to/search -type f -size +1M
      ```
   - **Execute a command on found files**:
      ```bash
      find /path/to/search -name "*.log" -exec rm {} \;
      ```

Experiment with different flags like `-user`, `-group`, and `-perm` to tailor your searches.


2. **Networking**: What is a firewall? How does it work?
   * **Firewall Definition**:
     A firewall is a network security system that monitors and controls incoming and outgoing traffic based on predefined security rules.

     **Types of Firewalls**:
   - **Packet Filtering Firewall**: Examines packets based on IP, port, and protocol.
   - **Stateful Inspection Firewall**: Tracks the state of active connections.
   - **Application Layer Firewall**: Analyzes application-specific protocols (e.g., HTTP, FTP).
   - **Next-Generation Firewall (NGFW)**: Includes features like intrusion prevention and deep packet inspection.

    **How It Works**:
  - Filters traffic based on rules (allow, block, reject).
  - Rules can be set for:
   - Source/destination IP addresses.
   - Source/destination ports.
   - Protocols (TCP, UDP, ICMP).

   Example of a simple `iptables` rule:
   ```bash
   iptables -A INPUT -p tcp --dport 22 -j ACCEPT
   ```
   This allows SSH (port 22) traffic.


3. **Cloud Computing**: Discuss the benefits of Elastic Block Store (EBS) volumes.
    *  **Benefits of EBS:**
   1. **Scalability**: Supports volumes up to 16 TiB.
   2. **High Performance**:
    - SSD options for low-latency, IOPS-intensive applications.
    - HDD options for throughput-intensive workloads.
   3. **Durability**: Replicated within the same Availability Zone (AZ) for fault tolerance.
   4. **Snapshots**: Easy backups to Amazon S3 for recovery or migration.
   5. **Flexibility**: Attach and detach volumes to EC2 instances as needed.
   6. **Encryption**: Built-in encryption to secure data at rest.
   7. **Cost-Effective**: Pay only for the provisioned storage.

   **Use Cases**:
    - Databases (e.g., MySQL, MongoDB).
    - Transaction-heavy workloads.
    - Hosting applications that require low-latency storage.


4. **DevOps**: Explain what Git branching strategies are and why they’re useful.

5. **Tools & Technology**: Set up Git with branching. Practice merging and resolving conflicts.

6. **Scenario**: A large team works on the same codebase. What Git strategies would you recommend?


