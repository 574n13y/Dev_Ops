# Day 45

1. **Linux**: Explore `lsof` to list open files.
   * The `lsof` command stands for **List Open Files** and is used to identify which files are opened by which processes.

   #### **Key Usage Examples**:
   - List all open files:
     ```bash
     lsof
     ```
   - List open files for a specific user:
     ```bash
     lsof -u username
     ```
   - Check which process is using a specific file:
     ```bash
     lsof /path/to/file
     ```
   - Check which process is using a specific port (e.g., 80):
     ```bash
     lsof -i :80
     ```
   - Kill a process holding a specific file:
     ```bash
     kill -9 $(lsof -t /path/to/file)
     ```

   #### **Use Cases**:
   - Debugging file locks.
   - Monitoring network connections.
   - Identifying processes blocking specific files or ports.


2. **Networking**: Explain IP forwarding and when it’s used.

3. **Cloud Computing**: Describe the purpose of AWS CloudFormation.

4. **DevOps**: What is A/B testing, and why is it used?

5. **Tools & Technology**: Write a simple CloudFormation template for a VPC.

6. **Scenario**: Your team needs automated cloud resources. How would you implement this?



