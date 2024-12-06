# Day 34


1. **Linux**: Practice with `tar` to compress and extract files.
   - **`tar` (Tape Archive)**: Used to archive multiple files into a single file or extract files from an archive.
  
   - **Basic Commands:**
    - **Compress Files:**
      ```bash
      tar -cvf archive.tar file1 file2
      ```
    - `-c`: Create a new archive.
    - `-v`: Verbose (shows progress).
    - `-f`: Specifies the archive file.

   - **Compress and Add Gzip:**
      ```bash
      tar -czvf archive.tar.gz file1 file2
      ```
    - `-z`: Compress with Gzip.

   - **Extract Files:**
      ```bash
      tar -xvf archive.tar
      ```
    - `-x`: Extract files.

   - **Extract Gzipped Archive:**
      ```bash
      tar -xzvf archive.tar.gz
      ```

   - **View Archive Contents:**
      ```bash
      tar -tvf archive.tar
      ```


2. **Networking**: Describe HTTP vs. HTTPS. What are the main differences?

3. **Cloud Computing**: Explain AWS EC2 instance types and use cases.

4. **DevOps**: What is configuration management? Describe its purpose.

5. **Tools & Technology**: Install and configure a basic Nginx server.

6. **Scenario**: Your team needs a static website. How would you deploy it on a server?

