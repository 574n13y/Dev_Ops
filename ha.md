# Day 61


1. **Linux**: Experiment with `netstat` for network diagnostics.
   - The `netstat` command is a powerful tool to analyze network connections, routing tables, and port usage.  
    - **Basic Usage**:  
      ```bash
      netstat -a  # Displays all connections and listening ports  
      netstat -t  # Shows TCP connections  
      netstat -u  # Shows UDP connections  
      netstat -l  # Lists listening ports  
      netstat -r  # Displays the kernel routing table  
      netstat -s  # Displays network statistics  
      ```

   - **Common Scenarios**:  
    - Check for open ports and their associated services.
    - Diagnose network performance issues.
    - Identify suspicious network activity.


2. **Networking**: Explain IP address classes.
   - IP addresses are categorized into five classes (A to E) based on their range and purpose.  

   | **Class** | **Range**                | **Default Subnet Mask** | **Usage**                      |  
   |-----------|--------------------------|--------------------------|--------------------------------|  
   | **A**     | 0.0.0.0 - 126.255.255.255 | 255.0.0.0                | Large networks (e.g., ISPs).  |  
   | **B**     | 128.0.0.0 - 191.255.255.255 | 255.255.0.0              | Medium-sized networks.        |  
   | **C**     | 192.0.0.0 - 223.255.255.255 | 255.255.255.0            | Small networks (e.g., LANs).  |  
   | **D**     | 224.0.0.0 - 239.255.255.255 | N/A                      | Multicasting.                 |  
   | **E**     | 240.0.0.0 - 255.255.255.255 | N/A                      | Reserved for future use.      |  
   
   * 127.0.0.1 is loopback address


3. **Cloud Computing**: Discuss how S3 storage tiers work.

4. **DevOps**: Define automated testing and its importance in CI/CD.

5. **Tools & Technology**: Set up a simple testing pipeline in Jenkins.

6. **Scenario**: You need to automate unit tests for every code push. How would you do it?

