# Day 37

1. **Linux**: Learn to use rsync to synchronize files.
#### **Key Points**
- **What is `rsync`?**
  - A Linux command-line utility for efficiently transferring and synchronizing files across directories or systems.
  - Supports incremental file transfers, ensuring only modified files are copied.

#### **Basic Commands**
- Sync files locally:
  ```bash
  rsync -av source_directory/ destination_directory/
  ```
- Sync files over SSH:
  ```bash
  rsync -av -e ssh source_directory/ user@remote_host:/path/to/destination/
  ```
- Perform a dry run:
  ```bash
  rsync -av --dry-run source_directory/ destination_directory/
  ```
- Exclude files or directories:
  ```bash
  rsync -av --exclude 'file_or_dir_name' source_directory/ destination_directory/
  ```

#### **Benefits**
- Efficient data transfer.
- Built-in compression with the `-z` flag.
- Useful for backups and migrations.

   
2. **Networking**: Explain the concept of load balancing and its benefits.

3. **Cloud Computing**: Describe Amazon RDS and its key features.

4. **DevOps**: What are secrets management and environment variables?

5. **Tools & Technology**: Install Vault for secret management and set up a basic secret.

6. **Scenario**: Your team needs to secure application credentials. How would you handle it?


