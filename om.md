# Day 36



1. **Linux**: Use `diff` to compare two files.
   * The `diff` command in Linux compares two files line by line and outputs the differences.  
    
     **Example Usage:**  
      ```bash
      diff file1.txt file2.txt
      ```
   - Output uses:  
    - `<` for lines in `file1` but not in `file2`.  
    - `>` for lines in `file2` but not in `file1`.  
     **Useful Options:**  
    - `diff -y file1.txt file2.txt`: Displays side-by-side comparison.  
    - `diff -c file1.txt file2.txt`: Context format to show surrounding lines for better understanding.


2. **Networking**: Explain SSL/TLS and how it secures data.
   * **SSL (Secure Sockets Layer)** and **TLS (Transport Layer Security)** are cryptographic protocols used to secure communication over a network.  
   
     **Key Features of SSL/TLS:**  
    - **Encryption:** Protects data in transit from eavesdropping.  
    - **Authentication:** Uses certificates to verify the identity of communicating parties.  
    - **Integrity:** Ensures transmitted data is not altered using message digests and hashing algorithms.  

   **How It Works:**  
   1. **Handshake Phase:**  
    - Client and server negotiate supported SSL/TLS versions and ciphers.  
    - Server presents its certificate, verified by the client.  
    - A shared session key is established for encryption.  
   2. **Data Transmission:**  
    - All communication is encrypted using the session key.  


3. **Cloud Computing**: What is an AWS VPC? Describe its basic components.
   * **AWS VPC (Virtual Private Cloud):**  
     A logically isolated network within AWS, enabling users to define and control network configurations similar to an on-premise data center.  

   **Key Components:**  
   - **Subnets:** Divides the VPC into public and private sections.  
   - **Route Tables:** Defines how traffic flows within the VPC and to external destinations.  
   - **Internet Gateway:** Allows access to the internet for resources in public subnets.  
   - **NAT Gateway:** Enables private subnet instances to access the internet without being directly exposed.  
   - **Security Groups and Network ACLs:** Control inbound and outbound traffic at the instance and subnet levels.  


4. **DevOps**: Describe the importance of backup and restore strategies.
   * **Backup and Restore Strategies Are Vital for:**  
    - **Data Protection:** Safeguarding against accidental deletions, corruption, or cyberattacks.  
    - **Business Continuity:** Ensuring quick recovery to minimize downtime during disasters.  
    - **Compliance:** Meeting regulatory requirements for data retention and recovery.  

   **Best Practices:**  
    - Automate backups with tools like `rsync` or cloud-native services.  
    - Use a combination of on-site, off-site, and cloud storage.  
    - Periodically test restore processes to ensure backup validity.  


5. **Tools & Technology**: Create a backup script using `rsync`.
   * The following script uses `rsync` to backup a directory to a remote server:  
    ```bash
    #!/bin/bash

    # Variables
    SOURCE="/path/to/source"
    DESTINATION="user@remote_server:/path/to/destination"
    LOGFILE="/path/to/backup.log"
    DATE=$(date +"%Y-%m-%d %H:%M:%S")

    # Run rsync
    rsync -avz --delete "$SOURCE" "$DESTINATION" &>> "$LOGFILE"

    # Log Completion
    echo "Backup completed at $DATE" >> "$LOGFILE"
    ```

   **Steps to Use:**  
    1. Replace `SOURCE`, `DESTINATION`, and `LOGFILE` with actual paths.  
    2. Schedule the script using `cron` for automation.  


6. **Scenario**: A system needs regular data backups. How would you automate them?

