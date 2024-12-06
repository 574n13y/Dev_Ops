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
   - Networking: HTTP vs. HTTPS**
     | Feature           | HTTP (HyperText Transfer Protocol)    | HTTPS (HTTP Secure)                      |
     |-------------------|----------------------------------------|------------------------------------------|
     | **Encryption**    | No encryption, plain text             | Encrypted using SSL/TLS                  |
     | **Port**          | Port 80                               | Port 443                                 |
     | **Security**      | Vulnerable to man-in-the-middle attacks | Protects data from eavesdropping         |
     | **Certificate**   | No certificates required              | Requires an SSL/TLS certificate          |
     | **Speed**         | Slightly faster due to no encryption   | Slightly slower due to encryption/decryption |

   - **Key Point:** Always use HTTPS for secure communications and to gain user trust.


3. **Cloud Computing**: Explain AWS EC2 instance types and use cases.
   - AWS EC2 offers various instance types categorized by their use cases:

     | **Type**      | **Purpose**                         | **Examples**                | **Use Cases**                         |
     |---------------|-------------------------------------|-----------------------------|---------------------------------------|
     | **General**   | Balanced compute, memory, storage  | `t2.micro`, `m5.large`      | Web servers, dev/test environments    |
     | **Compute**   | High CPU for compute-intensive tasks | `c5.large`, `c6g.large`    | Gaming, media encoding, scientific apps |
     | **Memory**    | High memory for large datasets     | `r5.large`, `x1e.xlarge`    | In-memory databases, analytics        |
     | **Storage**   | Optimized storage performance      | `i3.large`, `d2.large`      | Data warehouses, Big Data             |
     | **Accelerated**| GPUs for ML and graphics processing | `p3.large`, `g4dn.xlarge`   | AI/ML workloads, video rendering      |

   - **Key Factors for Selection:** 
    - Workload type, budget, performance requirements.


4. **DevOps**: What is configuration management? Describe its purpose.
   - **Definition:**
    - Configuration Management (CM) involves maintaining consistency of systems, software, and resources.
    - Tools ensure systems are in a desired state by automating configuration tasks.

   - **Purpose:**
    - Reduce configuration drift across environments.
    - Automate repetitive tasks.
    - Improve reliability and predictability.

   - **Examples of CM Tools:**
    - **Ansible:** Agentless, YAML-based.
    - **Chef:** Code-driven, Ruby-based.
    - **Puppet:** Declarative language for infrastructure.


5. **Tools & Technology**: Install and configure a basic Nginx server.

6. **Scenario**: Your team needs a static website. How would you deploy it on a server?

