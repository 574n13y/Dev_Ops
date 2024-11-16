# Day 24

---

1. **Linux**: Move files using the `mv` command.
  - The `mv` command in Linux is used to move or rename files and directories.  
    **Syntax**:  
    ```bash
    mv [options] source destination
    ```

    **Examples**:
   - Move a file:  
     ```bash
     mv file1.txt /home/user/documents/
     ```
   - Rename a file:  
     ```bash
     mv oldname.txt newname.txt
     ```
   - Move and overwrite without prompt:  
     ```bash
     mv -f file1.txt /home/user/documents/
     ```
   - Prompt before overwriting:  
     ```bash
     mv -i file1.txt /home/user/documents/
     ```


2. **Networking**: Explain the purpose of the `traceroute` command.
   
   - The `traceroute` command is a network diagnostic tool used to trace the path packets take from the source to the destination.

    **Purpose**:
   1. Identify intermediate routers/hops between two systems.
   2. Diagnose connectivity issues or identify bottlenecks.
   3. Understand network latency and routing.

   **Syntax**:
   ```bash
   traceroute [options] hostname_or_IP
   ```

   **Example**:
   ```bash
   traceroute google.com
   ```

   **Output**:
    The output displays the hops (routers) along the path and the response time for each hop.


3. **Cloud Computing**: Describe cloud regions and availability zones in AWS.
   - **Regions**:
    - Geographically isolated locations worldwide (e.g., `us-east-1`, `eu-west-1`).
    - Each region contains multiple availability zones.
    - Data transfer across regions incurs additional costs.

   - **Availability Zones (AZs)**:
    - Data centers within a region, isolated but interconnected.
    - Provide fault tolerance and high availability.
    - Examples: `us-east-1a`, `us-east-1b`.

   **Purpose**:
    - Regions ensure global coverage.
    - AZs enhance reliability and scalability by enabling redundancy.


4. **DevOps**: Explain the concept of Infrastructure as Code (IaC).
5. **Tools & Technology**: Install the AWS CLI and configure a user.
6. **Scenario**: A server needs to run scripts at specific intervals. How would you set this up?

