# Day 44

1. **Linux**: Practice with `ln` to create hard and symbolic links.
   - **Hard Links**:  
    - A hard link is a direct reference to the physical data on disk.
    - Deleting the original file doesn’t affect the hard link.

   **Command**:
     ```bash
     ln file1.txt hardlink_file1.txt
     ```

   **Verify**:
     ```bash
     ls -li
     ```

   - **Symbolic Links (Soft Links)**:  
    - A soft link is a pointer to the original file. It breaks if the original file is deleted.

   **Command**:
     ```bash
     ln -s file1.txt symlink_file1.txt
     ```

   **Verify**:
     ```bash
     ls -l
     ```


2. **Networking**: What is a default gateway, and why is it necessary?

3. **Cloud Computing**: Discuss the purpose of AWS Auto Scaling.

4. **DevOps**: Define continuous monitoring and its role in DevOps.

5. **Tools & Technology**: Set up monitoring in Grafana with a basic dashboard.

6. **Scenario**: An application needs real-time monitoring. How would you set it up?


