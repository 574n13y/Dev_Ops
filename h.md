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
   - **Subnet Mask**: A subnet mask divides an IP address into two parts: the network and host components. It defines the size of a network and determines which part identifies the network and which part identifies the host.  
   - **Example**:  
    - IP Address: `192.168.1.10`
    - Subnet Mask: `255.255.255.0` (CIDR: `/24`)
    - Network Portion: `192.168.1`
    - Host Portion: `.10`  

  Subnet masks enable efficient allocation of IP addresses and network segmentation.


3. **Cloud Computing**: Describe the concept of AWS Auto Scaling.
   - **Definition**:  
     AWS Auto Scaling automatically adjusts the number of instances in a fleet based on traffic patterns. It helps maintain application performance while minimizing costs.
   - **Key Features**:
    - **Dynamic Scaling**: Responds to real-time demand changes.
    - **Scheduled Scaling**: Scales based on predefined time patterns.
    - **Health Monitoring**: Replaces unhealthy instances.
   - **Use Cases**:
    - Traffic spikes (e.g., during a sale or product launch).
    - Seasonal workloads.


4. **DevOps**: Explain the role of a load balancer in a microservices architecture.
   - **Definition**:  
     A load balancer distributes incoming traffic across multiple servers to ensure no single server is overwhelmed.  
   - **Role in Microservices**:
    1. **Traffic Distribution**: Ensures even load distribution among microservices.
    2. **Health Monitoring**: Routes traffic only to healthy instances.
    3. **Failover**: Provides redundancy by rerouting traffic in case of a failure.
    4. **Service Discovery**: Helps manage service-to-service communication.
    5. **Improved User Experience**: Reduces latency and increases reliability.


5. **Tools & Technology**: Set up Auto Scaling for EC2 instances in AWS.

6. **Scenario**: Your application’s traffic fluctuates significantly. How would you ensure scalability?

