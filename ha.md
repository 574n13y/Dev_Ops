# Day 64

1. **Linux**: Use `rsync` to synchronize files between two directories.
   - **Command**:  
     To synchronize files from `source_directory` to `destination_directory`, use:
     ```bash
     rsync -avh /path/to/source_directory/ /path/to/destination_directory/
     ```

   - **Options**:  
    - `-a`: Archive mode (preserves symbolic links, permissions, timestamps, etc.).
    - `-v`: Verbose mode for detailed output.
    - `-h`: Human-readable file sizes.

   - **Example**:  
     Synchronize files from `/home/user/source` to `/home/user/destination`:
     ```bash
     rsync -avh /home/user/source/ /home/user/destination/
     ```


2. **Networking**: Explain BGP (Border Gateway Protocol) and where it’s used.

3. **Cloud Computing**: Discuss the use cases for AWS Elastic File System (EFS).

4. **DevOps**: What is immutable infrastructure, and why is it beneficial?

5. **Tools & Technology**: Set up a basic EFS instance and attach it to an EC2 instance.

6. **Scenario**: You need shared file storage across multiple instances. How would you configure this?

