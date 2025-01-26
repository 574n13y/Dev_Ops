# Day 72


1. **Linux**: Create simple shell scripts to automate repetitive tasks.
   - A script to back up a directory daily:
     
     ```bash
     #!/bin/bash
     SOURCE="/path/to/source"
     DEST="/path/to/backup"
     TIMESTAMP=$(date +%Y%m%d_%H%M%S)
     BACKUP="$DEST/backup_$TIMESTAMP.tar.gz"
     tar -czf "$BACKUP" "$SOURCE"
     echo "Backup completed: $BACKUP"
     ```
     Save this as `backup.sh`, make it executable using `chmod +x backup.sh`, and schedule it with `cron` for daily automation.


2. **Networking**: Explain IPv6 and its advantages over IPv4.
   - IPv6 is the next-generation internet protocol designed to replace IPv4.  

   **Advantages:**
    - **Larger Address Space**: IPv6 has 128-bit addresses, allowing for 3.4×10³⁸ unique addresses, compared to IPv4's 32-bit (4.3 billion addresses).
    - **Simplified Network Configuration**: Automatic address configuration without DHCP.
    - **Better Performance**: Optimized for routing and reduced fragmentation.
    - **Enhanced Security**: IPv6 natively supports IPsec for end-to-end encryption.
    - **Multicast Support**: Efficient bandwidth usage for streaming and data delivery.


3. **Cloud Computing**: Describe AWS KMS and its use in encryption.
   -  AWS Key Management Service (KMS) is a fully managed service for creating and controlling cryptographic keys.  

   **Uses:**
    - Encrypting data in services like S3, EBS, and RDS.
    - Managing keys securely through centralized control.
    - Using AWS KMS API to encrypt and decrypt application data.
    - Integration with AWS CloudTrail for auditing key usage.


4. **DevOps**: What is a release train, and how does it help in DevOps?
   - A release train is a scheduled and predictable release model, where features and updates are packaged and deployed at regular intervals (e.g., bi-weekly).  

   **Benefits:**
    - Ensures timely delivery of features.
    - Encourages cross-team collaboration by setting clear deadlines.
    - Reduces the risk of delays by focusing on smaller, manageable updates.
    - Aligns with Agile and Continuous Delivery principles.


5. **Tools & Technology**: Set up basic key management using AWS KMS.
   - Steps to create and use a KMS key:  
    
    1. **Create a KMS Key**:
    - Go to the AWS Management Console → KMS → Create Key.
    - Select **Symmetric Key** and configure permissions.
    
    2. **Encrypt Data**:
    - Use AWS CLI:
          ```bash
          aws kms encrypt --key-id <Key-ID> --plaintext fileb://data.txt --output text --query CiphertextBlob > encrypted_data.txt
          ```
   
    3. **Decrypt Data**:
    - Use AWS CLI:
          ```bash
          aws kms decrypt --ciphertext-blob fileb://encrypted_data.txt --output text --query Plaintext | base64 --decode > decrypted_data.txt
          ```
   
    4. **Integrate Key with Services** (e.g., S3, EBS, RDS).


6. **Scenario**: Your application needs secure key storage for API keys. How would you configure this?
   - Steps to use AWS KMS for secure API key storage:  
   
    1. **Encrypt API Keys**:
    - Use AWS KMS to encrypt sensitive keys before storing them in a database or configuration file.
   
    2. **Store Encrypted Keys Securely**:
    - Save encrypted keys in a secure location (e.g., AWS Secrets Manager or an encrypted S3 bucket).
   
    3. **Access Keys at Runtime**:
    - Decrypt keys programmatically using AWS SDKs or CLI.
   
    4. **Limit Permissions**:
    - Use IAM policies to restrict access to KMS keys and secrets to only authorized roles/services.
   
    5. **Enable Key Rotation**:
    - Configure automatic key rotation in AWS KMS to enhance security.

