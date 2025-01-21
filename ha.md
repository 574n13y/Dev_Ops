# Day 67

1. **Linux**: Use `find` with advanced filters to search for files by size and date.
   * The `find` command can be used with options like `-size` and `-mtime` to search for files.  
   **Examples**:  
    - Find files larger than 100MB:  
      ```bash
      find /path/to/search -type f -size +100M
      ```
    - Find files modified in the last 7 days:  
      ```bash
      find /path/to/search -type f -mtime -7
      ```
    - Combine both:  
      ```bash
      find /path/to/search -type f -size +100M -mtime -7
      ```  


2. **Networking**: Explain how SSL/TLS encryption works and its importance.
   * **How It Works**:  
    
    1. **Handshake Process**:  
    - A client requests a secure connection to a server.  
    - Server sends its **SSL/TLS certificate** (contains its public key).  
    - The client verifies the certificate using a trusted Certificate Authority (CA).  
    
    2. **Session Key Generation**:  
    - The client and server generate a shared session key using asymmetric encryption.  
    - This session key is used for encrypting data during the session.  
    
    3. **Data Encryption**:  
    - All communication is encrypted with the session key using symmetric encryption.  

   **Importance**:  
    - Ensures **data confidentiality** (prevents eavesdropping).  
    - Guarantees **integrity** (data isn’t altered in transit).  
    - Provides **authentication** (ensures the server is legitimate).  


3. **Cloud Computing**: Define data lifecycle management in AWS.
   * **Data Lifecycle Management (DLM)** in AWS is the process of automating the management of data stored in AWS services (e.g., S3, EBS). It optimizes costs by transitioning or deleting data based on its age or access patterns.  

   **Key Features**:  
    - **S3 Lifecycle Policies**: Transition objects to different storage classes like Standard, Infrequent Access (IA), or Glacier.  
    - **EBS Snapshots**: Automate the creation and deletion of EBS snapshots.  


4. **DevOps**: What is the role of automated deployment approval in CI/CD pipelines?
   * **Purpose**:  
    - Adds a layer of control to ensure deployments meet specific criteria before proceeding.  

   **How It Works**:  
    - Pipelines can include **manual approval steps**, where a stakeholder reviews and approves deployment.  
    - Automated approvals can be achieved through tests or policy checks (e.g., ensuring security scans or performance benchmarks are met).  

   **Benefits**:  
    - Prevents deployment of broken or non-compliant code.  
    - Enables controlled rollouts in production environments.  


5. **Tools & Technology**: Set up lifecycle policies for an S3 bucket.
   * **Steps**:  
    
    1. Go to the **S3 Console**.  
    
    2. Select the bucket and navigate to the **Management** tab.  
    
    3. Under **Lifecycle Rules**, create a new rule.  
    - **Name**: "Archive Old Files".  
    - **Scope**: Choose the prefix or apply it to the whole bucket.  
    
    4. Configure transitions:  
    - Move objects to **Glacier** after 90 days.  
    - Delete objects after 365 days.  
    
    5. Review and apply the policy.  

**Example Policy JSON**:  
    ```json
    {
      "Rules": [
        {
         "ID": "ArchiveOldFiles",
         "Filter": { "Prefix": "" },
         "Status": "Enabled",
         "Transitions": [
           {
             "Days": 90,
             "StorageClass": "GLACIER"
            }
           ],
           "Expiration": {
           "Days": 365
          }
        }
      ]
     }
    ```


6. **Scenario**: Your organization wants to automatically archive and delete older data. How would you configure this?

