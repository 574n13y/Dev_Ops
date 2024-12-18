# Day 42


1. **Linux**: Explain process management with `ps`, `top`, and `htop`.
   * Managing processes is an essential part of Linux system administration. Here's how these tools help:  

   - **`ps` (Process Status)**:  
     Provides a static snapshot of current processes. Common commands:  
    - `ps aux`: Displays all running processes with detailed information.  
    - `ps -e`: Shows all processes in a simplified format.  

   - **`top`**:  
     A real-time process monitoring tool.  
    - Shows CPU, memory usage, and running processes.  
    - Interactive features allow sorting or killing processes directly.  

   - **`htop`**:  
     An interactive, user-friendly alternative to `top`.  
    - Uses color coding to display resource usage.  
    - Allows searching, filtering, and process management via an intuitive interface.  


2. **Networking**: What is a VPN, and how does it secure data transmission?
   * A **VPN (Virtual Private Network)** is a technology that creates a secure, encrypted connection between your device and a remote server.  

   **How VPN Secures Data Transmission**:  
    1. **Encryption**: All data sent through the VPN is encrypted using protocols like OpenVPN, IKEv2, or WireGuard.  
    2. **Tunneling**: It encapsulates data within secure "tunnels," preventing unauthorized access.  
    3. **IP Masking**: Hides your real IP address by routing traffic through a VPN server.  
    4. **Data Integrity**: Ensures data is not tampered with during transmission.  


3. **Cloud Computing**: Explain AWS’s Shared Responsibility Model.
   * The AWS **Shared Responsibility Model** outlines the division of security responsibilities between AWS and its customers:  

   - **AWS’s Responsibility (Security *of* the Cloud)**:  
     AWS secures the underlying infrastructure, including hardware, software, networking, and physical facilities.  

   - **Customer’s Responsibility (Security *in* the Cloud)**:  
     Customers are responsible for managing the security of their applications, data, operating systems, and configurations.  

   **Example**:  
   - AWS manages EC2 infrastructure.  
   - Customers secure their EC2 instances, including firewall rules and application security.  


4. **DevOps**: What is version control, and why is it essential?
   * **Version Control** is the practice of tracking and managing changes to code or files over time.  

   **Why Version Control is Essential**:  
    1. **Collaboration**: Allows multiple developers to work on the same project simultaneously without conflicts.  
    2. **Tracking Changes**: Maintains a history of edits, enabling rollbacks to previous versions if needed.  
    3. **Branching and Merging**: Developers can create isolated branches for new features and merge them after testing.  
    4. **Backup**: Acts as a safety net, storing all versions of the code in a central repository.  

   **Popular Tools**: Git, Mercurial, and Subversion.  


5. **Tools & Technology**: Use Git to tag a release version in your repository.
   * **Git Tags** mark specific commits as important, often used for release versions.  

   **Steps to Tag a Release**:  
    1. Create a tag:  
       ```bash
       git tag -a v1.0 -m "Release version 1.0"
       ```  
    2. Push the tag to the remote repository:  
       ```bash
       git push origin v1.0
       ```  
    3. List all tags:  
       ```bash
       git tag
       ```  


6. **Scenario**: A new feature is released. How would you manage code versions for easy rollback?
   * To manage code versions for easy rollback:  

   1. **Use Git Branching**:  
    - Develop the feature in a separate branch (e.g., `feature/new-feature`).  
    - Merge the branch into `main` or `release` after testing.  

   2. **Tag Stable Releases**:  
    - Tag the production-ready code before deploying (e.g., `v1.0`, `v1.1`).  

   3. **Implement Rollback Strategy**:  
    - If the new feature breaks production, revert to a previous stable release:  
      ```bash
      git checkout v1.0
      git push origin main
      ```  

   4. **CI/CD Integration**:  
    - Automate testing to catch issues early.  
    - Deploy only after passing all tests.  

   5. **Maintain Backups**:  
    - Back up the database and application state before deploying major changes to ensure recovery if necessary.  

