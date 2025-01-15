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

4. **DevOps**: Describe how blue-green deployment reduces downtime.

5. **Tools & Technology**: Set up a blue-green deployment using AWS Elastic Beanstalk.

6. **Scenario**: Your team needs zero-downtime deployment. What would you recommend?


