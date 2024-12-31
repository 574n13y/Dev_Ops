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
   - **IPv6** (Internet Protocol Version 6) is the successor to IPv4, designed to address the exhaustion of IPv4 addresses. It provides:
    - A **128-bit address space**: ~340 undecillion unique addresses.
    - **Built-in security**: IPsec is mandatory for IPv6.
    - **Efficient routing and autoconfiguration**.
  
   #### **Why is IPv6 Important?**
    1. Addresses the **IPv4 address exhaustion**.
    2. Improves **performance** for large-scale networks.
    3. Facilitates **IoT** and other modern technologies requiring massive address allocation.


3. **Cloud Computing**: Describe how AWS Elastic Load Balancing (ELB) works.
   - **AWS ELB** automatically distributes incoming application traffic across multiple targets, such as EC2 instances, containers, and IP addresses.
  
   #### **Types of ELBs**:
    1. **Application Load Balancer (ALB)**:
    - Operates at the **Layer 7** (HTTP/HTTPS).
    - Ideal for microservices and content-based routing.
   
    2. **Network Load Balancer (NLB)**:
    - Operates at **Layer 4** (TCP/UDP).
    - Handles high-performance, low-latency traffic.
   
    3. **Gateway Load Balancer (GWLB)**:
    - Distributes traffic for virtual appliances.
   
    4. **Classic Load Balancer (CLB)**:
    - Operates at both Layer 4 and Layer 7.
    - Suitable for legacy applications.

   #### **How It Works**:
    1. Distributes traffic based on the configured routing rules.
    2. Monitors health of targets using health checks.
    3. Automatically scales based on traffic demands.


4. **DevOps**: What is canary deployment, and when would you use it?
   - **Canary Deployment** is a strategy where new changes are deployed to a small subset of users before being rolled out to the entire user base.
  
   #### **Key Features**:
    1. Gradual rollouts reduce risks associated with failures.
    2. Allows real-world testing for a controlled audience.
    3. Metrics and user feedback help validate the deployment.

   #### **When to Use It**:
    - Launching **new features**.
    - Rolling out **performance improvements**.
    - Deploying changes in **high-availability applications**.


5. **Tools & Technology**: Configure a load balancer on AWS.

6. **Scenario**: Your application requires gradual feature rollouts. Which deployment strategy would you choose?


