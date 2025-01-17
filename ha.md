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
   - **Definition**:  
Immutable infrastructure refers to a model where servers or resources are never modified after deployment. Any updates or changes are made by replacing the resource with a new version.

   **Benefits**:
    1. **Consistency**:
    - Ensures that each deployment is predictable and reproducible.
    2. **Simplifies Troubleshooting**:
    - Eliminates issues caused by configuration drift (untracked changes over time).
    3. **Improved Reliability**:
    - Reduces the risk of manual configuration errors.
    4. **Better Testing**:
    - Infrastructure updates can be tested in isolation before replacing the old version.
    5. **Easy Rollbacks**:
    - Rolling back to a previous version is straightforward since the old version remains untouched.


5. **Tools & Technology**: Set up a basic EFS instance and attach it to an EC2 instance.
   - **Steps**:
    
    1. **Create an EFS File System**:
    - Go to the **EFS Console** in AWS.
    - Click **Create File System** and configure:
    * **VPC**: Select the appropriate VPC.
    * **Mount Targets**: Enable mount targets for the subnets where your EC2 instances are running.
    - Save and create.
    
    2. **Attach EFS to an EC2 Instance**:
    - Install the NFS client on the EC2 instance:
      ```bash
      sudo yum install -y nfs-utils    # For Amazon Linux or RHEL
      sudo apt-get install -y nfs-common # For Ubuntu/Debian
      ```
    - Create a directory to mount the EFS:
      ```bash
      sudo mkdir /mnt/efs
      ```
    - Mount the EFS:
      ```bash
      sudo mount -t nfs4 -o nfsvers=4.1 fs-XXXXXXX.efs.YOUR_REGION.amazonaws.com:/ /mnt/efs
      ```
    
    3. **Test the Setup**:
    - Write a file to the `/mnt/efs` directory from one instance and verify its availability on another instance using the same mount target.


6. **Scenario**: You need shared file storage across multiple instances. How would you configure this?

