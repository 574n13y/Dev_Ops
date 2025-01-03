# Day 49

1. **Linux**: Use `df -h` and `du -sh` to monitor disk usage.
   - **`df -h`**:
    - Displays disk space usage for all mounted filesystems in human-readable format.
    - Example:
      ```bash
      df -h
      ```
    Output includes total size, used, available space, and mount points.

  - **`du -sh`**:
    - Calculates the disk usage of files or directories.
    - Example:
      ```bash
      du -sh /path/to/directory
      ```
    Output shows the size of the specified directory in human-readable format.

  **Use Case**:  
  Combine both commands to monitor overall and specific disk usage.


2. **Networking**: Describe the concept of VLANs and how they work in networking.
   - **What is a VLAN?**
    - A **Virtual Local Area Network (VLAN)** is a logical grouping of devices in the same broadcast domain, even if they are physically in different locations.

   - **How It Works**:
    - VLANs use **tagging** (802.1Q standard) to separate traffic between devices.
    - A VLAN ID (1–4094) is assigned to each group of devices.
    - Switches route traffic between VLANs using VLAN tags.

   - **Advantages**:
    - Improves **network segmentation** and security.
    - Reduces broadcast traffic.
    - Simplifies network management.


3. **Cloud Computing**: Explain AWS IAM policies and how to attach them to users or groups.
   - **What are IAM Policies?**
    - JSON documents defining permissions for AWS services and resources.
    - Types of Policies:
    1. **Managed Policies**: Predefined by AWS or created by the user.
    2. **Inline Policies**: Directly attached to a user, group, or role.

   - **Key Elements**:
    - **Version**: Specifies the policy language version.
    - **Statement**: Defines permissions (effect, action, resource, condition).

   - **Attaching Policies**:
    - To a user:
      ```bash
      aws iam attach-user-policy --user-name <user_name> --policy-arn <policy_arn>
      ```
    - To a group:
      ```bash
      aws iam attach-group-policy --group-name <group_name> --policy-arn <policy_arn>
      ```


4. **DevOps**: What are the key principles of GitOps?
   - **GitOps Principles**:
    1. **Versioned Infrastructure**: Store infrastructure definitions in Git.
    2. **Declarative Configuration**: Define the desired system state in code.
    3. **Automated Deployment**: Use CI/CD pipelines to apply changes.
    4. **Self-Healing Systems**: Continuously sync the desired state using tools like ArgoCD or Flux.
    5. **Auditability**: Every change is recorded in Git, ensuring traceability.

   - **Why GitOps?**
    - Ensures consistency, scalability, and fast recovery during failures.


5. **Tools & Technology**: Install Ansible and write a basic playbook to install Apache.
   * **Installation**:
   1. Install Ansible:
      ```bash
      sudo apt update
      sudo apt install ansible -y
      ```
   2. Verify installation:
      ```bash
      ansible --version
      ```

   **Write a Playbook**:
   - Create a file named `apache_install.yml`:
     ```yaml
     ---
     - name: Install Apache Web Server
       hosts: all
       become: true
       tasks:
         - name: Install Apache
           apt:
             name: apache2
             state: present

         - name: Ensure Apache is running
             service:
             name: apache2
             state: started
             enabled: true
     ```

   **Run the Playbook**:
   1. Create an inventory file `inventory`:
      ```
      [web]
      <your_server_ip> ansible_user=ubuntu ansible_ssh_private_key_file=<path_to_private_key>
      ```

   2. Execute the playbook:
      ```bash
      ansible-playbook -i inventory apache_install.yml
      ```


6. **Scenario**: Your organization wants automated server setups. How would you implement this with Ansible?
   - **Implementation Plan**:
   1. **Centralized Playbooks**:
    - Create playbooks to standardize server configurations (e.g., installing software, configuring firewalls).
   2. **Inventory Management**:
    - Use dynamic inventory for cloud environments like AWS.
   3. **CI/CD Integration**:
    - Automate playbook execution using Jenkins or GitLab CI/CD pipelines.
   4. **Testing**:
    - Use tools like Molecule to test playbooks.



