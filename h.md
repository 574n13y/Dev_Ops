# Day 54

1. **Linux**: Use `iptables` for basic firewall configurations.
   * **Concept**:  
`iptables` is a command-line utility used to configure Linux kernel firewall rules. It manages incoming and outgoing traffic based on defined rules.

   * **Examples**:  
    - **Block Incoming Traffic on Port 80**:  
      ```bash
      sudo iptables -A INPUT -p tcp --dport 80 -j DROP
      ```
    - **Allow SSH Traffic**:  
      ```bash
      sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
      ```
    - **View Rules**:  
      ```bash
      sudo iptables -L -v
      ```


2. **Networking**: What is a subnet mask? How is it used in IP addressing?

3. **Cloud Computing**: Describe the concept of AWS Auto Scaling.

4. **DevOps**: Explain the role of a load balancer in a microservices architecture.

5. **Tools & Technology**: Set up Auto Scaling for EC2 instances in AWS.

6. **Scenario**: Your application’s traffic fluctuates significantly. How would you ensure scalability?

