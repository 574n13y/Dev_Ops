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

4. **DevOps**: What are the key principles of GitOps?

5. **Tools & Technology**: Install Ansible and write a basic playbook to install Apache.

6. **Scenario**: Your organization wants automated server setups. How would you implement this with Ansible?


