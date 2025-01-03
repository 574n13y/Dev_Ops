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
   - **Traditional CI/CD**:
    - Focuses on automating build, test, and deploy pipelines.
    - Developers manually trigger deployments or use pipeline triggers.
   - **GitOps**:
    - Entire infrastructure and application state is stored as code in Git repositories.
    - Deployments are triggered by changes to the Git repository.
    - Uses tools like ArgoCD or Flux to reconcile desired and actual states.

   **Key Benefits of GitOps**:
    - Enhanced auditability (all changes are in Git).
    - Better collaboration (Git as the single source of truth).
    - Faster rollback by reverting Git commits.


5. **Tools & Technology**: Create a simple playbook in Ansible to install NGINX on multiple servers.
   * **Inventory File (hosts.yml):**
     ```yaml
     [web_servers]
     server1 ansible_host=192.168.1.101 ansible_user=ubuntu
     server2 ansible_host=192.168.1.102 ansible_user=ubuntu
     ```

   * **Ansible Playbook (install_nginx.yml):**
     ```yaml
     - name: Install and configure NGINX on web servers
       hosts: web_servers
       become: true
       tasks:
         - name: Update apt cache
            apt:
             update_cache: yes

         - name: Install NGINX
            apt:
             name: nginx
             state: present

         - name: Ensure NGINX is running
             service:
             name: nginx
             state: started
             enabled: true
     ```

   **Execute Playbook:**
     ```bash
     ansible-playbook -i hosts.yml install_nginx.yml
     ```


6. **Scenario**: Your team needs to provision a web server fleet. How would you automate it?
   - Use **Ansible** to automate the installation of web servers like NGINX or Apache.
   - Steps:
    1. Create an inventory file for the target servers.
    2. Write a playbook to install and configure the web server.
    3. Use dynamic inventory if the servers are hosted in the cloud (e.g., AWS EC2).
    4. Schedule the playbook to run periodically or on-demand using tools like Jenkins or cron.

   **Example Workflow:**
   1. **Provision Servers**: Use Terraform to create EC2 instances.
   2. **Automate Setup**: Run the Ansible playbook to install NGINX.
   3. **Load Balancing**: Integrate with AWS ALB (Application Load Balancer) for scalability.



