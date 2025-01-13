# Day 60


1. **Linux**: Use `top` to monitor system resources in real time.
* The `top` command in Linux allows you to monitor system resources and processes in real time. Here's how to use it:

- **Launch `top`**: Run `top` in your terminal.
- **Key Metrics**:
  - **CPU Usage**: Percentage of CPU used by processes.
  - **Memory Usage**: RAM consumption by the system and processes.
  - **Load Average**: System load over the last 1, 5, and 15 minutes.
  - **Processes**: Number of total, running, sleeping, and zombie processes.
- **Interactive Commands**:
  - `k`: Kill a process (enter the PID when prompted).
  - `r`: Change the priority (nice value) of a process.
  - `q`: Quit the `top` command.
  - `h`: View help for additional commands.


2. **Networking**: Define network packets and their components.
* A **network packet** is a formatted unit of data carried across a network. Its components include:

- **Header**:
  - **Source Address**: The IP address of the sender.
  - **Destination Address**: The IP address of the recipient.
  - **Protocol**: Specifies the protocol used (e.g., TCP, UDP).
  - **Sequence Number**: Identifies the order of the packet in a transmission.
  - **Checksum**: Ensures data integrity.
  
- **Payload**:
  - Contains the actual data being transmitted (e.g., part of a file, a message).
  
- **Trailer**:
  - Marks the end of the packet and may include error-checking data (e.g., cyclic redundancy check).


3. **Cloud Computing**: Describe EC2 Auto Scaling policies.
* EC2 Auto Scaling policies automatically manage the number of Amazon EC2 instances in a group based on application demand or predefined schedules. Key policies include:

1. **Target Tracking Scaling**:
   - Adjusts the number of instances to maintain a specified metric at a target value.
   - Example: Keeping CPU utilization at 50%.

2. **Step Scaling**:
   - Adds or removes instances based on metric thresholds that trigger step adjustments.
   - Example: Adding 2 instances if CPU utilization exceeds 70%.

3. **Scheduled Scaling**:
   - Scales the number of instances based on a predefined schedule.
   - Example: Increasing instance count during peak business hours.

4. **Predictive Scaling**:
   - Uses machine learning to predict future demand and scales capacity in advance.


4. **DevOps**: What are the best practices for secrets management?
* Managing secrets (e.g., API keys, passwords) securely is crucial. Best practices include:

1. **Centralized Secrets Management**:
   - Use tools like AWS Secrets Manager, HashiCorp Vault, or Azure Key Vault to securely store and access secrets.
   
2. **Avoid Hardcoding Secrets**:
   - Do not store secrets in code repositories or configuration files.

3. **Environment Variables**:
   - Load secrets into applications via environment variables instead of embedding them in the code.

4. **Access Control**:
   - Follow the principle of least privilege to restrict access to secrets.

5. **Encryption**:
   - Encrypt secrets at rest and in transit.

6. **Rotate Secrets Regularly**:
   - Periodically update and rotate secrets to minimize the impact of exposure.

7. **Audit and Monitor**:
   - Log and monitor access to secrets to detect unauthorized usage.


5. **Tools & Technology**: Set up AWS Secrets Manager for storing API keys.
1. **Create a Secret**:
   - Open AWS Secrets Manager and choose **Store a new secret**.
   - Select the type of secret (e.g., API key) and input the key-value pair(s).

2. **Define Access Policies**:
   - Use IAM policies to control who can access the secret.

3. **Enable Encryption**:
   - Secrets are automatically encrypted using AWS KMS.

4. **Retrieve the Secret**:
   - Use the AWS SDK, CLI, or Secrets Manager console to fetch the secret.
   - Example CLI command:  
     ```bash
     aws secretsmanager get-secret-value --secret-id <SECRET_NAME>
     ```

5. **Integrate with Applications**:
   - Use environment variables or directly access the secret programmatically using the AWS SDK.


6. **Scenario**: Your app requires secure management of sensitive data. How would you handle it?
* To securely manage sensitive data in your application:

1. **Use AWS Secrets Manager**:
   - Store sensitive information like API keys, database credentials, and encryption keys securely.
   - Implement IAM policies to ensure only authorized applications and users can access the secrets.

2. **Environment Variables**:
   - Load secrets into environment variables during application runtime.

3. **Encryption**:
   - Encrypt sensitive data using AWS KMS or a similar encryption service.

4. **Automated Rotation**:
   - Configure automated secret rotation in AWS Secrets Manager to minimize risks associated with long-lived credentials.

5. **Audit and Monitoring**:
   - Use AWS CloudTrail to log access to secrets and monitor unusual activity.

6. **Infrastructure as Code**:
   - Use tools like CloudFormation or Terraform to manage secret configurations programmatically while keeping them out of source code.

This approach ensures the sensitive data is protected against unauthorized access while being easily accessible to authorized resources and applications.

