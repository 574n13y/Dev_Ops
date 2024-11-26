# Day 29


1. **Linux**: Describe the `top` command and its usage.
  * The `top` command in Linux is used to monitor system performance in real time. It displays information about processes and system resource usage, such as CPU, memory, and swap. Key features include:  
   - **Process Table:** Shows active processes sorted by CPU usage (default).  
   - **Dynamic Updates:** Data updates every few seconds (customizable).  
   - **Interactive Options:**  
    - `k` to kill a process.  
    - `r` to renice a process.  
    - `P` to sort by CPU usage or `M` for memory.  
   - **Usage Example:**  
     ```bash
     top
     ```
     Press `q` to exit.  


2. **Networking**: Explain ARP and how it works.
  * **ARP** maps an IP address to a physical MAC address on a local network. It operates within the Link Layer of the OSI model.  

   - **How it works:**  
    1. When a device wants to communicate with another device on the same network, it checks its ARP table for the MAC address of the target IP.  
    2. If the MAC address is missing, it sends a broadcast ARP request.  
    3. The device with the requested IP responds with its MAC address.  
    4. The sender updates its ARP table and proceeds with communication.  

   - **Command Example:**  
     ```bash
     arp -a
     ```
  This displays the ARP cache.  


3. **Cloud Computing**: Discuss the benefits of serverless architecture.
  * Serverless architecture allows developers to build and run applications without managing servers. The cloud provider handles the infrastructure.  

   - **Benefits:**  
    - **Cost Efficiency:** Pay only for execution time (e.g., per function invocation).  
    - **Scalability:** Automatically scales up or down based on demand.  
    - **Reduced Operational Overhead:** No server management, patching, or provisioning required.  
    - **Faster Time-to-Market:** Focus solely on application logic.  
    - **Event-Driven:** Ideal for applications with unpredictable workloads or microservices.  


4. **DevOps**: What’s the difference between continuous delivery and continuous deployment?

5. **Tools & Technology**: Set up a basic Jenkins job.

6. **Scenario**: An application needs automated testing before deployment. How would you set this up?


