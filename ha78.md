# Day 78


1. **Linux**: Set up user permissions with `usermod`, `groupadd`, and `chmod`.
   - Managing user permissions is critical for security and access control in Linux.  

   - **`usermod`**: Modify user properties (e.g., adding a user to a group).  
     ```bash
     sudo usermod -aG developers alice  # Add 'alice' to the 'developers' group
     ```
   - **`groupadd`**: Create a new group.  
     ```bash
     sudo groupadd admins
     ```
   - **`chmod`**: Change file permissions.  
     ```bash
     chmod 750 script.sh  # Only owner and group can execute
     ```


2. **Networking**: Explain VPNs and their role in secure remote access.
   - A **Virtual Private Network (VPN)** allows secure remote access by encrypting traffic between a client and a private network.  

   - **Use Cases**:  
    - Secure access to internal cloud resources.  
    - Encrypt data between remote employees and corporate networks.  
    - Connect multiple cloud environments securely (e.g., AWS VPN, OpenVPN).  

   - **Example: AWS Client VPN**  
    - AWS offers **Client VPN** for secure, managed VPN connectivity.  
    - Supports **SSL-based** authentication.  


3. **Cloud Computing**: Define AWS Organizations and its use in multi-account setups.
   - AWS Organizations helps manage multiple AWS accounts with centralized governance.  

   - **Features**:  
    - **Centralized Billing**: One consolidated bill for multiple accounts.  
   - **Service Control Policies (SCPs)**: Restrict access across accounts.  
   - **OU (Organizational Units)**: Group accounts based on teams or functions.  

   - **Example Structure**:  
     ```
     Root Account  
     ├── Security OU  
     │   ├── Security Account  
     ├── Development OU  
     │   ├── Dev Account  
     ├── Production OU  
         ├── Prod Account  
     ```

   - **Command to Enable AWS Organizations** (CLI):  
     ```bash
     aws organizations enable-aws-service-access --service-principal organizations.amazonaws.com
     ```


4. **DevOps**: Explain deployment rollbacks and how to handle failed deployments.
   - A **rollback** is reverting an application to a previous stable state when a deployment fails.  

   #### **Best Practices for Handling Rollbacks**  
    
    1. **Use Blue-Green or Canary Deployments**  
    - **Blue-Green**: Deploy a new version alongside the old one and switch traffic.  
    - **Canary**: Gradually shift traffic to the new version.  
    
    2. **Automate Rollbacks**  
    - Use **AWS CodeDeploy** with **automatic rollback**:  
      ```yaml
      rollbackConfiguration:
        rollbackEnabled: true
      ```
    
    3. **Version Control & Database Migrations**  
    - Keep old versions available.  
    - Use **feature flags** to disable features without redeploying.  


5. **Tools & Technology**: Set up AWS Organizations and create a sub-account.
   - To set up **AWS Organizations** and add a sub-account:  
    
    1. **Enable AWS Organizations**:  
       ```bash
       aws organizations enable-aws-service-access --service-principal organizations.amazonaws.com
       ```
    
    2. **Create a new sub-account**:  
       ```bash
       aws organizations create-account --email "dev-team@example.com" --account-name "DevTeam"
       ```
    
    3. **Move the sub-account to an Organizational Unit (OU)**:  
       ```bash
       aws organizations move-account --account-id 123456789012 --source-parent-id r-abc1 --destination-parent-id ou-xyz1
       ```


6. **Scenario**: Your company needs centralized account management for different teams. How would you organize it?
   * **Solution:** Use **AWS Organizations** with **OU (Organizational Units)** and **IAM policies**.  

   #### **Proposed AWS Account Structure:**
        ```
        Root Account  
        ├── Security OU  
        │   ├── Security Logging Account  
        │   ├── IAM Audit Account  
        ├── Development OU  
        │   ├── Dev Account  
        │   ├── Staging Account  
        ├── Production OU  
        │   ├── Prod Account  
        │   ├── Backup Account  
        ```

   **Implementation Steps:**  
    1. **Enable AWS Organizations & Create OUs**  
    2. **Apply SCPs (Service Control Policies)**  
    - Example: Restrict access to delete resources in production.  
      ```json
      {
        "Effect": "Deny",
        "Action": "ec2:TerminateInstances",
        "Resource": "*"
      }
      ```
    3. **Enable AWS SSO (Single Sign-On) for team access**  
    4. **Use AWS CloudTrail & AWS Config for compliance monitoring**  

---

### **Final Thoughts**  
AWS Organizations is a **best practice** for managing **multiple AWS accounts** efficiently. It ensures **cost optimization, security, and governance**.  


