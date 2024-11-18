# Day 25
---

1. **Linux**: Explain the difference between hard and soft links. Create an example.
   #### **Hard Links**
    - Directly reference the inode (physical location on disk) of a file.
    - Changes made to the original file are reflected in the hard link.
    - Even if the original file is deleted, the hard link retains the data.

   #### **Soft Links (Symbolic Links)**
    - A shortcut pointing to the original file’s path.
    - If the original file is deleted, the soft link becomes broken.
    - Can link across different file systems or partitions.

   #### **Example**
    ```bash
    # Create a file
    echo "Hello, World!" > original.txt

    # Create a hard link
    ln original.txt hardlink.txt

    # Create a soft link
    ln -s original.txt softlink.txt
    ```

   #### **Verify**
    ```bash
    ls -li
    ```
This will show identical inodes for `original.txt` and `hardlink.txt`, while `softlink.txt` has a different inode.


2. **Networking**: What are network layers, and how do they work?
3. **Cloud Computing**: Describe AWS IAM roles and policies.
4. **DevOps**: Explain the benefits of containerization.
5. **Tools & Technology**: Use Docker to create a custom image.
6. **Scenario**: An application needs to run on multiple servers. How would you design the deployment?


