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

3. **Cloud Computing**: Explain the purpose of AWS EC2 AMIs (Amazon Machine Images).

4. **DevOps**: Describe how GitOps is different from traditional CI/CD.

5. **Tools & Technology**: Create a simple playbook in Ansible to install NGINX on multiple servers.

6. **Scenario**: Your team needs to provision a web server fleet. How would you automate it?


