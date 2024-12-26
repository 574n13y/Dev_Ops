# Day 48

1. **Linux**: Practice file compression using `gzip` and `bzip2`.
   - **`gzip`**:
    - Compress a file:
      ```bash
      gzip filename
      ```
    - Decompress a file:
      ```bash
      gunzip filename.gz
      ```
    - View compression ratio:
      ```bash
      gzip -l filename.gz
      ```

   - **`bzip2`**:
    - Compress a file:
      ```bash
      bzip2 filename
      ```
    - Decompress a file:
      ```bash
      bunzip2 filename.bz2
      ```
    - Faster compression with `pbzip2` (parallel version of bzip2):
      ```bash
      pbzip2 filename
      ```

   **Key Differences**:
   - `gzip`: Faster, less compression.
   - `bzip2`: Slower, better compression.



2. **Networking**: Explain the purpose and basics of IPsec.
   - **What is IPsec?**  
  Internet Protocol Security (IPsec) is a suite of protocols designed to secure IP communications by authenticating and encrypting each packet in a data stream.

   - **Purpose**:
    - Provides **data integrity**, **authentication**, and **encryption**.
    - Protects data during transit over untrusted networks like the Internet.
    - Used in VPNs (Virtual Private Networks) to secure connections.

   - **Key Components**:
    1. **Authentication Header (AH)**: Ensures data integrity and authenticity.
    2. **Encapsulating Security Payload (ESP)**: Provides confidentiality, integrity, and authentication.
    3. **IKE (Internet Key Exchange)**: Establishes security associations and manages encryption keys.



3. **Cloud Computing**: Describe AWS Elastic File System (EFS) and its use cases.

4. **DevOps**: What is release management, and why is it important?

5. **Tools & Technology**: Use Terraform to deploy an EFS mount to an EC2 instance.

6. **Scenario**: A high-availability application needs shared storage. What AWS solution would you recommend?

