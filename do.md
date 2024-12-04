# Day 31

---

1. **Linux**: Use `chmod` for setting file permissions.
   - **Command**:  
  `chmod` changes file and directory permissions in Linux. Permissions are read (`r`), write (`w`), and execute (`x`), and they apply to the file owner, group, and others.  
   - **Examples**:  
    - Grant execute permission to the owner:  
      ```bash
      chmod u+x file.txt
      ```
    - Set permissions to read and write for the owner, and read-only for others:  
      ```bash
      chmod 644 file.txt
      ```
    - Allow everyone full permissions (not recommended):  
      ```bash
      chmod 777 file.txt
      ```


2. **Networking**: Explain VPN and its usage.
   - **Definition**:  
  A **Virtual Private Network (VPN)** creates a secure and encrypted connection over a public network, enabling users to access resources securely.  
   - **Key Uses**:  
    - Protects data transmission over public networks.  
    - Provides remote workers access to company resources securely.  
    - Bypasses geographic restrictions on content.  
    - Ensures privacy by masking the user’s IP address.  


3. **Cloud Computing**: Describe an EC2 instance and its purpose.
4. **DevOps**: Explain Infrastructure as Code and its benefits.
5. **Tools & Technology**: Install Ansible and run a basic playbook.
6. **Scenario**: Your team needs secure remote access to an application. What would you set up?
