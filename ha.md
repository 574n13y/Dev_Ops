# Day 64

1. **Linux**: Use `rsync` to synchronize files between two directories.
   - **Command**:  
     To synchronize files from `source_directory` to `destination_directory`, use:
     ```bash
     rsync -avh /path/to/source_directory/ /path/to/destination_directory/
     ```

   - **Options**:  
    - `-a`: Archive mode (preserves symbolic links, permissions, timestamps, etc.).
    - `-v`: Verbose mode for detailed output.
    - `-h`: Human-readable file sizes.

   - **Example**:  
     Synchronize files from `/home/user/source` to `/home/user/destination`:
     ```bash
     rsync -avh /home/user/source/ /home/user/destination/
     ```


2. **Networking**: Explain BGP (Border Gateway Protocol) and where it’s used.
   - **BGP Overview**:  
   Border Gateway Protocol (BGP) is the protocol used to exchange routing information between different autonomous systems (AS) on the internet. It ensures data is routed efficiently across various networks.

   - **Use Cases**:
    1. **Internet Service Providers (ISPs)**:
    - ISPs use BGP to exchange routing information and ensure global internet connectivity.
    2. **Cloud Providers**:
    - AWS, Azure, and Google Cloud use BGP for connectivity in hybrid cloud environments.
    3. **Enterprises**:
    - Large organizations use BGP to manage traffic between their on-premises data centers and cloud environments.


3. **Cloud Computing**: Discuss the use cases for AWS Elastic File System (EFS).
   - AWS EFS provides a scalable, managed file storage solution that can be accessed by multiple EC2 instances simultaneously.

   **Use Cases**:
    1. **Shared File Storage**:
    - Applications requiring shared access across multiple instances, like content management systems.
    2. **Big Data Analytics**:
    - Enables parallel processing by multiple compute nodes accessing the same data.
    3. **Backup and Restore**:
    - Centralized storage for backups accessible across different applications or regions.
    4. **Web Hosting**:
    - Hosts static files (e.g., images, HTML) that need to be served to multiple web servers.
    5. **Containerized Applications**:
    - Provides persistent storage for containers in Kubernetes or ECS.


4. **DevOps**: What is immutable infrastructure, and why is it beneficial?

5. **Tools & Technology**: Set up a basic EFS instance and attach it to an EC2 instance.

6. **Scenario**: You need shared file storage across multiple instances. How would you configure this?

