# Day 65

1. **Linux**: Explore disk space and inode usage using `df` and `du`.
  - **`df`** (Disk Free):
   - Displays disk space usage for file systems.
   - Example command:
    ```bash
    df -h
    ```
    - `-h`: Human-readable format (e.g., MB, GB).

  - **`du`** (Disk Usage):
   - Shows directory/file space usage.
   - Example command:
    ```bash
    du -sh /path/to/directory
    ```
    - `-s`: Summarize total size.
    - `-h`: Human-readable format.

  - **Inode Usage**:
   - Use `df` to view inode usage:
    ```bash
    df -i
    ```
    - Displays available and used inodes (useful for systems with many small files).


2. **Networking**: What is a firewall, and how does it help in network security?

3. **Cloud Computing**: Describe VPC subnetting and how it improves network segmentation.

4. **DevOps**: Define configuration drift and how to detect it.

5. **Tools & Technology**: Use Terraform to create a VPC with subnets.

6. **Scenario**: You need a VPC with public and private subnets. How would you design this?

