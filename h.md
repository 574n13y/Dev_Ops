# Day 51

1. **Linux**: Use mount and umount to mount and unmount filesystems.
   - **Mounting**:
    - The `mount` command is used to attach a filesystem to a specific directory (known as a mount point) in the Linux filesystem hierarchy.
    - Example:
    ```bash
    sudo mount /dev/sdb1 /mnt/mydrive
    ```
    Here:
    - `/dev/sdb1` is the device or partition you want to mount.
    - `/mnt/mydrive` is the directory where the filesystem will be accessible.

   - To mount with options (e.g., read-only):
    ```bash
    sudo mount -o ro /dev/sdb1 /mnt/mydrive
    ```

  - **Unmounting**:
   - The `umount` command detaches a mounted filesystem.
   - Example:
     ```bash
     sudo umount /mnt/mydrive
     ```
     Alternatively, you can use the device name:
     ```bash
     sudo umount /dev/sdb1
     ```

2. **Networking**: Explain ARP (Address Resolution Protocol) and its role in networking.

3. **Cloud Computing**: Describe the process of creating a custom AMI.

4. **DevOps**: What is continuous deployment, and how is it implemented?

5. **Tools & Technology**: Set up a basic environment variable file in Ansible.

6. **Scenario**: Your web servers need customized configurations. How would you manage this across multiple servers?


