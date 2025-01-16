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

3. **Cloud Computing**: Explain the role of AWS CloudTrail.

4. **DevOps**: What’s the difference between Canary and A/B testing?

5. **Tools & Technology**: Use CloudTrail to track account activity.

6. **Scenario**: Your app needs to meet compliance standards. How would you ensure activity logging?


