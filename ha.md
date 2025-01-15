# Day 62


1. **Linux**: Use `lsof` to check open files and sockets.
   - **Command**: `lsof` (List Open Files) is a powerful Linux utility used to list all open files and the processes that opened them.  
   - **Use Cases**:  
    - Diagnose file-related issues (e.g., files that can't be deleted because they're in use).  
    - Identify network connections (e.g., sockets and ports in use).  
    - Monitor system activity.  
   - **Examples**:  
    - List all open files: `lsof`  
    - Check processes using a specific port: `lsof -i :8080`  
    - Find open files for a specific user: `lsof -u username`


2. **Networking**: Explain port forwarding and its applications.
   - **Definition**: Port forwarding is a technique used to redirect network traffic from one port or address to another.  
   - **How it Works**: Traffic arriving at a public IP and specific port is forwarded to a private IP and port inside a network.  
   - **Applications**:  
    - Accessing services hosted on private networks (e.g., accessing a web server in a home network).  
    - Enabling remote desktop or SSH connections.  
    - Gaming and hosting online services.


3. **Cloud Computing**: Discuss VPC peering in AWS.
   - **Definition**: VPC Peering allows two Virtual Private Clouds (VPCs) in AWS to communicate privately over the AWS backbone without traversing the public internet.  
   - **Use Cases**:  
    - Connecting services in different VPCs for cross-region replication or shared resources.  
    - Multi-account setups where teams use separate VPCs but require secure communication.  
   - **Advantages**:  
    - Low-latency communication.  
    - No additional hardware required.  
    - Simple and scalable for interconnecting VPCs.


4. **DevOps**: Describe how blue-green deployment reduces downtime.
   - **Definition**: Blue-green deployment is a deployment strategy where two environments are maintained:  
    - **Blue**: Current production version.  
    - **Green**: New version ready for release.  
   - **Process**:  
    - The green environment is tested while the blue environment serves traffic.  
    - Once the green environment is validated, traffic is switched to it (using DNS or a load balancer).  
    - In case of issues, traffic can be switched back to the blue environment.  
   - **Benefits**:  
    - Minimizes downtime.  
    - Simplifies rollback in case of issues.  
    - Provides a staging environment identical to production.


5. **Tools & Technology**: Set up a blue-green deployment using AWS Elastic Beanstalk.

6. **Scenario**: Your team needs zero-downtime deployment. What would you recommend?


