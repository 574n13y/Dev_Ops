# Day 26

---

1. **Linux**: Use the `rm` command to delete files and directories.
   * The `rm` command in Linux is used to delete files and directories. It removes the file entries from the file system and frees up the associated disk space.  

#### Syntax:  
```bash
rm [options] <file/directory>
```

#### Examples:  
- **Delete a single file:**  
  ```bash
  rm file.txt
  ```  
- **Delete multiple files:**  
  ```bash
  rm file1.txt file2.txt
  ```  
- **Delete a directory and its contents recursively:**  
  ```bash
  rm -r directory/
  ```  
- **Force delete without confirmation:**  
  ```bash
  rm -rf directory/
  ```  
**Caution:** Use `rm -rf` carefully as it permanently deletes files and directories.


2. **Networking**: Explain the purpose of a subnet mask.
   * A **subnet mask** is a 32-bit number used in IP networking to divide an IP address into two parts:
    1. **Network Portion**: Identifies the network to which the device belongs.  
    2. **Host Portion**: Identifies individual devices within the network.  

#### Purpose:
- **Subnetting**: Helps partition a larger network into smaller, manageable sub-networks.
- **Efficient IP Usage**: Reduces wastage of IP addresses.
- **Improved Security**: Isolates segments for better access control.

#### Example:
For the IP address `192.168.1.10` with a subnet mask of `255.255.255.0`:
- **Network Portion**: `192.168.1.0`
- **Host Portion**: `.10`


3. **Cloud Computing**: Describe the role of Elastic Load Balancer (ELB) in AWS.

4. **DevOps**: Describe the differences between development and production environments.

5. **Tools & Technology**: Use Docker Compose to start multiple containers.

6. **Scenario**: How would you isolate development and production environments in the cloud?





