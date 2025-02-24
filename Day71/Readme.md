# Day 71


1. **Linux**: Set up basic SSH configurations and keys.
   * Steps to Configure SSH and Keys:  
    
    1. **Generate SSH Keys**:  
       ```bash
       ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
       ```
    - Save the key pair to a location (default is `~/.ssh/id_rsa`).
    - Add a passphrase for additional security.
    
    2. **Copy Public Key to Remote Server**:  
       ```bash
       ssh-copy-id user@remote_server
       ```
   This adds the public key to the `~/.ssh/authorized_keys` file on the remote server.
    
    3. **Set Up SSH Config File**:  
       Create or edit the SSH config file:  
       ```bash
       nano ~/.ssh/config
       ```
      Example configuration:  
      ```
      Host my-server
          HostName 192.168.1.100
          User user
          IdentityFile ~/.ssh/id_rsa
      ```
      Connect using:  
      ```bash
      ssh my-server
      ```


2. **Networking**: Describe the differences between public and private IP addresses.

   | **Public IP Address**                         | **Private IP Address**                      |
   |-----------------------------------------------|---------------------------------------------|
   | Globally unique, used for internet access.    | Local to a private network, not routable on the internet. |
   | Assigned by ISPs and managed by IANA.         | Reserved by RFC 1918 (e.g., 192.168.x.x, 10.x.x.x). |
   | Used for web servers, email servers, etc.     | Used for internal communication within a network. |
   | Accessible from anywhere on the internet.     | Requires NAT or a gateway to communicate with the internet. |



3. **Cloud Computing**: Explain cross-region replication in S3.
   * **What Is Cross-Region Replication (CRR)?**
Cross-Region Replication (CRR) is an Amazon S3 feature that automatically replicates objects from a bucket in one AWS region to another bucket in a different region.

   * **Key Features**:
    - Ensures **high availability** and **disaster recovery**.
    - Supports **asynchronous replication**.
    - Allows replication of **specific prefixes or tags**.

   * **Use Cases**:
    - Compliance with data residency regulations.
    - Reducing latency by serving content closer to users in different regions.
    - Backup and disaster recovery.


4. **DevOps**: What is the purpose of feature flags in deployments?
   * **What Are Feature Flags?**
     Feature flags (or toggles) are a technique used to enable or disable specific application features without deploying new code.

   * **Benefits**:
    1. **Controlled Rollouts**: Gradually roll out features to subsets of users.
    2. **Risk Mitigation**: Roll back features quickly without redeploying.
    3. **A/B Testing**: Test variations of a feature to optimize performance or user experience.
    4. **Continuous Delivery**: Deploy code to production while keeping unfinished features hidden.


5. **Tools & Technology**: Configure cross-region replication for an S3 bucket.
   * Steps to Set Up CRR:
    1. **Create Two Buckets in Different Regions**:
       ```bash
       aws s3api create-bucket --bucket source-bucket-name --region us-east-1
       aws s3api create-bucket --bucket destination-bucket-name --region us-west-2
       ```
    
    2. **Enable Versioning on Both Buckets**:
       ```bash
       aws s3api put-bucket-versioning --bucket source-bucket-name --versioning-configuration Status=Enabled
       aws s3api put-bucket-versioning --bucket destination-bucket-name --versioning-configuration Status=Enabled
       ```
    
    3. **Create an IAM Role for Replication**:
    - Define a trust policy and attach permissions for the replication role.
    
    4. **Add a Replication Rule**:
       Example JSON policy for replication:
       ```json
       {
           "Rules": [
               {
                   "Status": "Enabled",
                   "Prefix": "",
                   "Destination": {
                       "Bucket": "arn:aws:s3:::destination-bucket-name"
                   }
               }
            ]
        }
       ```
       Apply the replication rule:
       ```bash
        aws s3api put-bucket-replication --bucket source-bucket-name --replication-configuration file://replication.json
       ```


6. **Scenario**: You need to replicate data across regions for high availability. How would you set this up?
   * Steps:
    1. **Set Up CRR as Described Above**.
    
    2. **Test Replication**:
    - Upload an object to the source bucket:
        ```bash
        aws s3 cp file.txt s3://source-bucket-name/
        ```
    - Verify the object appears in the destination bucket:
        ```bash
        aws s3 ls s3://destination-bucket-name/
        ```
    
    3. **Monitor Replication Status**:
   Use Amazon CloudWatch or the AWS Management Console to monitor replication activity and troubleshoot any issues.


