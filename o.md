# Day 33



1. **Linux**: Understand `chown` and change file ownership.
   - **`chown` Syntax:**
       ```bash
       chown [OPTIONS] USER[:GROUP] FILE
       ```
   - **Examples:**
    - Change file owner:
      ```bash
      sudo chown user1 file.txt
      ```
    - Change owner and group:
      ```bash
      sudo chown user1:group1 file.txt
      ```
    - Recursively change ownership:
      ```bash
      sudo chown -R user1:group1 /path/to/directory
      ```

   - **Why It’s Important:**
    - Controls file access by defining ownership.
    - Helps maintain security and permissions in multi-user environments.


2. **Networking**: Explain OSI Model layers.

3. **Cloud Computing**: Set up a simple Lambda function.

4. **DevOps**: Describe a build pipeline and how it works.

5. **Tools & Technology**: Use Terraform to create an EC2 and a security group.

6. **Scenario**: A client needs an autoscaling app. How would you set this up?

