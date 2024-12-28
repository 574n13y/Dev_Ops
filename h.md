# Day 50

1. **Linux**: Use `ps aux` to view all running processes and interpret columns.
   - The `ps aux` command lists all running processes in Linux.
   - Key columns to understand:
    - **USER**: The owner of the process.
    - **PID**: The Process ID.
    - **%CPU**: CPU usage percentage.
    - **%MEM**: Memory usage percentage.
    - **VSZ**: Virtual memory size used by the process.
    - **RSS**: Resident Set Size (physical memory used).
    - **TTY**: Terminal controlling the process.
    - **STAT**: Process state (e.g., R for running, S for sleeping).
    - **START**: Time when the process started.
    - **TIME**: CPU time consumed.
    - **COMMAND**: The command used to start the process.

   **Command Example:**
     ```bash
     ps aux | grep nginx
     ```


2. **Networking**: What is DHCP, and how does it assign IP addresses?
   - **Dynamic Host Configuration Protocol (DHCP)** automates the assignment of IP addresses, subnet masks, gateways, and DNS servers to devices on a network.
    - A DHCP server maintains a pool of IP addresses and assigns them dynamically to clients.
   - Process:
    1. **Discover**: Client broadcasts a DHCP discover message.
    2. **Offer**: DHCP server responds with an available IP.
    3. **Request**: Client requests the offered IP.
    4. **Ack**: Server acknowledges and assigns the IP.

   **Use Case**:
    - Ensures efficient use of IP addresses in large networks.
    - Reduces manual configuration errors.


3. **Cloud Computing**: Explain the purpose of AWS EC2 AMIs (Amazon Machine Images).
   - **Amazon Machine Images (AMIs)** are pre-configured virtual machine templates that include:
    - Operating system (e.g., Ubuntu, Amazon Linux).
    - Application software.
    - Custom configurations.
   - AMIs allow you to:
    - Quickly launch new instances with identical configurations.
    - Create backups of your current EC2 instances.
    - Share pre-configured environments across accounts.

   **Types of AMIs**:
    - **Public**: Shared by AWS or other users.
    - **Private**: Created by you and only accessible to your account.
    - **AWS Marketplace**: Paid AMIs with third-party software.


4. **DevOps**: Describe how GitOps is different from traditional CI/CD.

5. **Tools & Technology**: Create a simple playbook in Ansible to install NGINX on multiple servers.

6. **Scenario**: Your team needs to provision a web server fleet. How would you automate it?


