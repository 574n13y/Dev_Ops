# Day 59

1. **Linux**: Use `df` and `du` for detailed disk usage insights.
   - **`df` (Disk Free)**: Provides an overview of disk space usage for file systems.
    - Example usage:
    ```bash
    df -h
    ```
    - `-h`: Displays output in human-readable format (e.g., MB, GB).
    - Output includes file system, used and available space, and mount points.

   - **`du` (Disk Usage)**: Shows detailed space usage for directories and files.
    - Example usage:
    ```bash
    du -h /path/to/directory
    ```
    - `-h`: Human-readable format.
    - Can use `du -sh` for a summary of total space used by a directory.

   Combine both tools for a comprehensive view of disk usage:
    ```bash
    df -h
    du -sh /var/log
    ```


2. **Networking**: Describe TCP three-way handshake.

3. **Cloud Computing**: Explain the difference between EC2 and Lambda.

4. **DevOps**: What are build artifacts, and how do you manage them?

5. **Tools & Technology**: Configure an S3 bucket as an artifact repository.

6. **Scenario**: Your team wants to store build artifacts. How would you set this up?


