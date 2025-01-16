# Day 63

1. **Linux**: Configure SSH key-based authentication.
   * **Steps**:  
    1. **Generate an SSH Key Pair**:
       ```bash
       ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
       ```
      This creates two files:
    - Public key: `id_rsa.pub`
    - Private key: `id_rsa`
 
    2. **Copy the Public Key to the Remote Server**:
      ```bash
      ssh-copy-id username@remote_host
      ```
      Alternatively, manually append the public key to `~/.ssh/authorized_keys` on the server.
 
    3. **Set Proper Permissions**:
      ```bash
      chmod 700 ~/.ssh
      chmod 600 ~/.ssh/authorized_keys
      ```
    
    4. **Disable Password Authentication for Security**:
    - Edit `/etc/ssh/sshd_config`:
      ```
      PasswordAuthentication no
      ```
    - Restart the SSH service:
      ```bash
      sudo systemctl restart sshd
      ```


2. **Networking**: Describe DNS resolution.
   * **DNS Resolution** is the process of translating human-readable domain names (e.g., `example.com`) into IP addresses. It works as follows:
    1. **Query Initiation**: A user’s device sends a DNS query to a recursive resolver.
    2. **Recursive Resolver**:
    - Checks its cache for the IP address.
    - If not found, it queries a root DNS server.
    3. **Root Server**: Directs the resolver to the appropriate Top-Level Domain (TLD) nameserver (e.g., `.com`).
    4. **TLD Nameserver**: Directs the resolver to the authoritative nameserver for the domain.
    5. **Authoritative Nameserver**: Provides the IP address of the requested domain.
    6. **Response**: The resolver returns the IP address to the client.


3. **Cloud Computing**: Explain the role of AWS CloudTrail.
    - AWS CloudTrail is a service that enables governance, compliance, and operational auditing by logging account activity.  

   **Key Features**:
    - **Activity Logging**: Tracks API calls, SDK calls, CLI commands, and console actions.
    - **Event History**: Provides detailed records of changes to AWS resources.
    - **Compliance**: Helps meet regulatory requirements by maintaining an audit trail.
    - **Integration**: Works with Amazon S3 for log storage and CloudWatch for real-time monitoring.

   **Use Case**: Investigating unauthorized access or troubleshooting service configuration changes.


4. **DevOps**: What’s the difference between Canary and A/B testing?

   | **Aspect**         | **Canary Testing**                                   | **A/B Testing**                                 |
   |---------------------|-----------------------------------------------------|------------------------------------------------|
   | **Purpose**         | Gradual deployment of new features to monitor impact. | Compare two versions to evaluate user behavior.|
   | **Focus**           | Operational stability and performance.              | User experience and preference.               |
   | **Audience**        | Limited subset of users for operational testing.    | Split users into groups for testing variations.|
   | **Example**         | Deploying a new API version to 10% of traffic.      | Testing two UI designs to see which performs better.|


5. **Tools & Technology**: Use CloudTrail to track account activity.

6. **Scenario**: Your app needs to meet compliance standards. How would you ensure activity logging?


