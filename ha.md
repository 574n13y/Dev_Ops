# Day 66

1. **Linux**: Manage file compression using gzip and tar.
  - **`gzip`**: Compresses files into `.gz` format.
   - Example: Compress a file
    ```bash
    gzip file.txt
    ```
    - Result: `file.txt.gz`
   - Decompress:
    ```bash
    gunzip file.txt.gz
    ```

  - **`tar`**: Archives multiple files into one and optionally compresses them.
   - Create a `.tar` archive:
    ```bash
    tar -cvf archive.tar file1 file2 directory/
    ```
    - `-c`: Create
    - `-v`: Verbose (show progress)
    - `-f`: Output file

   - Compress with `gzip`:
    ```bash
    tar -czvf archive.tar.gz file1 file2 directory/
    ```

   - Extract an archive:
    ```bash
    tar -xzvf archive.tar.gz
    ```


2. **Networking**: Explain the difference between Layer 4 and Layer 7 load balancing.

3. **Cloud Computing**: What is AWS Transit Gateway, and how does it work?

4. **DevOps**: Discuss the principles of continuous testing.

5. **Tools & Technology**: Configure an AWS Transit Gateway for VPC peering.

6. **Scenario**: Your organization needs a central routing solution across multiple VPCs. How would you implement this?

