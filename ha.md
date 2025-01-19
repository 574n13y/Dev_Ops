# Day 65

1. **Linux**: Explore disk space and inode usage using `df` and `du`.
  - **`df`** (Disk Free):
   - Displays disk space usage for file systems.
   - Example command:
    ```bash
    df -h
    ```
    - `-h`: Human-readable format (e.g., MB, GB).

  - **`du`** (Disk Usage):
   - Shows directory/file space usage.
   - Example command:
    ```bash
    du -sh /path/to/directory
    ```
    - `-s`: Summarize total size.
    - `-h`: Human-readable format.

  - **Inode Usage**:
   - Use `df` to view inode usage:
    ```bash
    df -i
    ```
    - Displays available and used inodes (useful for systems with many small files).


2. **Networking**: What is a firewall, and how does it help in network security?
   - **Firewall Definition**:
  A firewall is a network security device or software that monitors and controls incoming and outgoing traffic based on predefined security rules.

   - **How It Helps in Security**:
    1. **Traffic Filtering**: Blocks unauthorized access while allowing legitimate traffic.
    2. **Prevents Attacks**: Protects against malicious traffic, such as DDoS, port scanning, and exploits.
    3. **Access Control**: Defines rules to permit or deny specific IPs, protocols, or ports.
    4. **Segmentation**: Enforces isolation between network zones.


3. **Cloud Computing**: Describe VPC subnetting and how it improves network segmentation.
   - **VPC Subnetting**:
    - Subnetting divides a VPC CIDR block into smaller subnets.
    - Subnets can be public (accessible from the internet) or private (restricted to internal resources).
  
   - **Improving Network Segmentation**:
    1. **Isolation**: Public-facing and internal resources are separated.
    2. **Security**: Fine-grained control over access using security groups and Network ACLs.
    3. **Efficient Routing**: Configures route tables for optimized traffic flow.


4. **DevOps**: Define configuration drift and how to detect it.

5. **Tools & Technology**: Use Terraform to create a VPC with subnets.

6. **Scenario**: You need a VPC with public and private subnets. How would you design this?

