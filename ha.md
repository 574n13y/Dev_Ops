# Day 69

1. **Linux**: Use `chmod` and `chown` to set permissions and ownership.
   
   - **`chmod`**: Used to modify file permissions for the owner, group, and others.  
    - Example: `chmod 755 file.txt` gives the owner read/write/execute permissions and the group/others read/execute permissions.  
   
   - **`chown`**: Changes ownership of a file or directory.  
    - Example: `chown user:group file.txt` sets `user` as the owner and `group` as the group owner.  
    - Combined Example: `sudo chown user:group file.txt && chmod 640 file.txt` sets `user` as the owner, `group` as the group owner, and gives read/write to the owner, read to the group, and no permissions to others.  


2. **Networking**: Explain the concept of DMZ (Demilitarized Zone) in networking.
  
   - **DMZ Definition**: A DMZ is a separate, isolated network zone between a secure internal network and an untrusted external network (e.g., the internet).  
   
   - **Purpose**:  
    - Hosts public-facing services like web servers, mail servers, and DNS servers.  
    - Acts as a buffer to minimize the risk of exposing internal networks to threats.  
   
   - **Implementation**: Typically achieved using firewalls to control traffic between the internal network, DMZ, and the internet.


3. **Cloud Computing**: Describe S3 bucket policies and their usage.
   - **Bucket Policies**: JSON-based access control policies for AWS S3 buckets.  
   
   - **Use Cases**:  
    - Allow or deny access to specific users or groups.  
    - Set permissions based on IP addresses, AWS services, or specific actions (e.g., read-only or upload).  
   - **Key Components**:  
    - **Principal**: Specifies the user or service.  
    - **Action**: Defines the operations (e.g., `s3:GetObject`).  
    - **Resource**: Identifies the S3 bucket or object.  
    - **Condition**: Adds filters (e.g., IP address, tags).  


4. **DevOps**: Define canary deployment and its purpose.
   - **Canary Deployment**: Gradually rolling out a new application version to a subset of users while monitoring its performance before full deployment.  
   
   - **Purpose**:  
    - Reduce risk by testing changes in a controlled manner.  
    - Rollback easily if issues are detected.  

   - **Example Use Case**: Rolling out new API changes to 5% of users, monitoring for errors, and incrementally increasing the rollout.


5. **Tools & Technology**: Configure a simple bucket policy in S3.
   - **Example Policy**: Grant public read access to files in a bucket.  
     ```json
     {
       "Version": "2012-10-17",
        "Statement": [
          {
           "Sid": "PublicReadGetObject",
           "Effect": "Allow",
           "Principal": "*",
           "Action": "s3:GetObject",
           "Resource": "arn:aws:s3:::example-bucket/*"
          }
        ]
     }
     ```  
   - **Steps**:  
    1. Navigate to the S3 console.  
    2. Select the bucket and go to the **Permissions** tab.  
    3. Add the JSON policy under **Bucket Policy**.  


6. **Scenario**: You need public and private access to different folders in an S3 bucket. How would you set it up?

