# Day 59

1. **Linux**: Use `df` and `du` for detailed disk usage insights.
   - **`df` (Disk Free)**: Provides an overview of disk space usage for file systems.
    - Example usage:
    ```bash
    df -h
    ```
    - `-h`: Displays output in human-readable format (e.g., MB, GB).
    - Output includes file system, used and available space, and mount points.

   - **`du` (Disk Usage)**: Shows detailed space usage for directories and files.
    - Example usage:
    ```bash
    du -h /path/to/directory
    ```
    - `-h`: Human-readable format.
    - Can use `du -sh` for a summary of total space used by a directory.

   Combine both tools for a comprehensive view of disk usage:
    ```bash
    df -h
    du -sh /var/log
    ```


2. **Networking**: Describe TCP three-way handshake.
   - The TCP three-way handshake establishes a reliable connection between a client and server:

   1. **SYN** (Synchronize): The client sends a SYN packet to initiate the connection, indicating it wants to establish communication.

   2. **SYN-ACK**: The server responds with a SYN-ACK packet to acknowledge the client’s request and indicates it is ready to establish a connection.

   3. **ACK** (Acknowledge): The client sends an ACK packet to acknowledge the server’s response, completing the handshake.

Once the handshake is complete, data transmission begins. This process ensures reliability and agreement on connection parameters.


3. **Cloud Computing**: Explain the difference between EC2 and Lambda.
   
   | **Aspect**         | **EC2 (Elastic Compute Cloud)**                                           | **Lambda**                                                |
   |---------------------|---------------------------------------------------------------------------|----------------------------------------------------------|
   | **Type**           | Virtual server for hosting applications.                                 | Serverless compute service.                              |
   | **Management**     | Requires manual management of servers, OS, and scaling.                  | Fully managed by AWS, no server management required.     |
   | **Billing**        | Pay for the uptime of the instance, whether idle or in use.              | Pay only for execution time (per invocation).            |
   | **Scalability**    | Requires manual setup or auto-scaling configuration.                     | Automatically scales with demand.                        |
   | **Use Cases**      | Hosting web apps, databases, or applications requiring persistent compute.| Running event-driven tasks or short-lived functions.     |


4. **DevOps**: What are build artifacts, and how do you manage them?
   - **Build Artifacts**: Files generated during the build process, such as binaries, JAR files, Docker images, or compiled assets. These are essential for deploying applications.

   **Management**:
    1. **Storage**: Use centralized repositories like AWS S3, JFrog Artifactory, or Nexus for storing artifacts.
    2. **Versioning**: Tag artifacts with version numbers or commit hashes to enable traceability.
    3. **Retention**: Implement policies to delete old artifacts and reduce storage costs.
    4. **Access Control**: Use IAM roles or repository settings to control who can read or write artifacts.
    5. **Automation**: Integrate artifact management into CI/CD pipelines using tools like Jenkins or GitLab CI.


5. **Tools & Technology**: Configure an S3 bucket as an artifact repository.
   1. **Create an S3 Bucket**:
   ```bash
   aws s3 mb s3://my-artifact-repository
   ```

   2. **Enable Versioning**:
   ```bash
   aws s3api put-bucket-versioning --bucket my-artifact-repository --versioning-configuration Status=Enabled
   ```

   3. **Set Access Control**:
   - Use a bucket policy to restrict access:
     ```json
     {
       "Version": "2012-10-17",
       "Statement": [
         {
           "Effect": "Allow",
           "Principal": { "AWS": "arn:aws:iam::123456789012:role/MyRole" },
           "Action": "s3:*",
           "Resource": "arn:aws:s3:::my-artifact-repository/*"
         }
       ]
     }
     ```
   - Apply the policy:
     ```bash
     aws s3api put-bucket-policy --bucket my-artifact-repository --policy file://bucket-policy.json
     ```

   4. **Upload Artifacts**:
   ```bash
   aws s3 cp artifact.zip s3://my-artifact-repository/builds/
   ```

   5. **Integrate with CI/CD**: Update pipeline scripts to upload/download artifacts from the S3 bucket.


6. **Scenario**: Your team wants to store build artifacts. How would you set this up?


