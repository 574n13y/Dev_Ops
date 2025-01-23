# Day 69

1. **Linux**: Use `chmod` and `chown` to set permissions and ownership.
   - **`chmod`**: Used to modify file permissions for the owner, group, and others.  
    - Example: `chmod 755 file.txt` gives the owner read/write/execute permissions and the group/others read/execute permissions.  
   - **`chown`**: Changes ownership of a file or directory.  
    - Example: `chown user:group file.txt` sets `user` as the owner and `group` as the group owner.  
    - Combined Example: `sudo chown user:group file.txt && chmod 640 file.txt` sets `user` as the owner, `group` as the group owner, and gives read/write to the owner, read to the group, and no permissions to others.  


2. **Networking**: Explain the concept of DMZ (Demilitarized Zone) in networking.

3. **Cloud Computing**: Describe S3 bucket policies and their usage.

4. **DevOps**: Define canary deployment and its purpose.

5. **Tools & Technology**: Configure a simple bucket policy in S3.

6. **Scenario**: You need public and private access to different folders in an S3 bucket. How would you set it up?

