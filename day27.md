# Day 27


1. **Linux**: Use the `cat` command to view files. What other options are available?
    * The `cat` command is used to read and concatenate files. Besides viewing files, it supports several options:

- **Basic Usage**:  
  ```bash
  cat filename
  ```

- **Options**:  
  - `-n`: Number all lines.  
    ```bash
    cat -n filename
    ```
  - `-b`: Number non-blank lines only.  
    ```bash
    cat -b filename
    ```
  - `-s`: Suppress repeated blank lines.  
    ```bash
    cat -s filename
    ```
  - `-E`: Show end-of-line characters (`$`).  
    ```bash
    cat -E filename
    ```

Other tools like `less`, `more`, or `head`/`tail` can be alternatives for specific needs.


2. **Networking**: Define the term "default gateway."
    * A **default gateway** is a network node that serves as an access point to another network, typically outside the local subnet. It’s often used to connect devices to the internet.

- **Purpose**:  
  The default gateway directs traffic to destinations not within the local network by forwarding packets to an external router.

- **Example**:  
  If a device on a local network (192.168.1.10) wants to communicate with a public server (8.8.8.8), the default gateway (e.g., 192.168.1.1) handles this routing.


3. **Cloud Computing**: Explain the AWS Shared Responsibility Model.
    * The AWS Shared Responsibility Model outlines the security responsibilities shared between AWS and the customer.

- **AWS Responsibility** (*Security of the Cloud*):  
  - Physical infrastructure, networking, and hypervisors.
  - Core services (e.g., storage, databases, compute).

- **Customer Responsibility** (*Security in the Cloud*):  
  - Data protection and encryption.
  - IAM (Identity and Access Management) configuration.
  - Application security and patching.

- **Example**:  
  AWS secures the S3 infrastructure, but you (the customer) must configure bucket permissions to prevent unauthorized access.


4. **DevOps**: Describe the importance of monitoring in DevOps.
    * Monitoring is crucial in DevOps for maintaining system reliability and performance. It enables teams to:

- **Detect Issues Early**: Identify and resolve problems before they impact users.
- **Ensure Uptime**: Monitor metrics like CPU, memory, and response times to prevent downtime.
- **Enable Continuous Improvement**: Gather data to optimize applications and infrastructure.
- **Support Collaboration**: Share insights across teams to align development and operations goals.

- **Example**:  
  Tools like **Prometheus** and **Grafana** are often used to monitor and visualize system health in real time.


5. **Tools & Technology**: Set up a basic Docker network between two containers.
    * To set up a network connecting two containers:

1. **Create a Custom Network**:  
   ```bash
   docker network create my-network
   ```

2. **Run Two Containers on the Same Network**:  
   ```bash
   docker run -dit --name container1 --network my-network alpine
   docker run -dit --name container2 --network my-network alpine
   ```

3. **Test Connectivity Between Containers**:  
   - Log into `container1`:  
     ```bash
     docker exec -it container1 sh
     ```
   - Ping `container2` by its name:  
     ```bash
     ping container2
     ```


6. **Scenario**: You need to troubleshoot connectivity issues between two containers. What steps would you take?
    * Steps to troubleshoot connectivity issues:

1. **Verify Network Configuration**:
   - List available networks:  
     ```bash
     docker network ls
     ```
   - Inspect the network:  
     ```bash
     docker network inspect my-network
     ```

2. **Check Container Connectivity**:
   - Log into one container and test connectivity using `ping` or `curl`.

3. **Firewall and Port Issues**:
   - Ensure the container’s exposed ports are correctly mapped:
     ```bash
     docker ps
     ```
   - Check firewall rules on the host system.

4. **DNS Resolution**:
   - Test if containers resolve each other by name:
     ```bash
     ping container-name
     ```

5. **Inspect Logs**:
   - Review logs of the failing container:
     ```bash
     docker logs container-name
     ```

