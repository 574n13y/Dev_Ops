# Day 53


1. **Linux**: Practice working with symbolic and hard links using `ln -s`.
   - **Symbolic Links (`ln -s`)**: A shortcut to a file or directory that can point across different file systems.
  ```bash
  # Create a symbolic link
  ln -s /path/to/original /path/to/link
  ```
   - If the original file is moved or deleted, the symbolic link breaks.

   - **Hard Links**: A direct reference to the file's inode, making it indistinguishable from the original.
  ```bash
  # Create a hard link
  ln /path/to/original /path/to/link
  ```
    - Cannot span different file systems.
    - If the original file is deleted, the hard link still functions.

   #### **Practice Task**:
    1. Create a file: `echo "Hello" > file.txt`.
    2. Create a symbolic link: `ln -s file.txt symlink.txt`.
    3. Create a hard link: `ln file.txt hardlink.txt`.
    4. Experiment with deleting the original file and observe the behavior of both links.


2. **Networking**: What is IPv6, and why is it important?

3. **Cloud Computing**: Describe how AWS Elastic Load Balancing (ELB) works.

4. **DevOps**: What is canary deployment, and when would you use it?

5. **Tools & Technology**: Configure a load balancer on AWS.

6. **Scenario**: Your application requires gradual feature rollouts. Which deployment strategy would you choose?


