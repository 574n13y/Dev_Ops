# Day 26

---

1. **Linux**: Use the `rm` command to delete files and directories.
   * The `rm` command in Linux is used to delete files and directories. It removes the file entries from the file system and frees up the associated disk space.  

#### Syntax:  
```bash
rm [options] <file/directory>
```

#### Examples:  
- **Delete a single file:**  
  ```bash
  rm file.txt
  ```  
- **Delete multiple files:**  
  ```bash
  rm file1.txt file2.txt
  ```  
- **Delete a directory and its contents recursively:**  
  ```bash
  rm -r directory/
  ```  
- **Force delete without confirmation:**  
  ```bash
  rm -rf directory/
  ```  
**Caution:** Use `rm -rf` carefully as it permanently deletes files and directories.


2. **Networking**: Explain the purpose of a subnet mask.
   * A **subnet mask** is a 32-bit number used in IP networking to divide an IP address into two parts:
    1. **Network Portion**: Identifies the network to which the device belongs.  
    2. **Host Portion**: Identifies individual devices within the network.  

#### Purpose:
- **Subnetting**: Helps partition a larger network into smaller, manageable sub-networks.
- **Efficient IP Usage**: Reduces wastage of IP addresses.
- **Improved Security**: Isolates segments for better access control.

#### Example:
For the IP address `192.168.1.10` with a subnet mask of `255.255.255.0`:
- **Network Portion**: `192.168.1.0`
- **Host Portion**: `.10`


3. **Cloud Computing**: Describe the role of Elastic Load Balancer (ELB) in AWS.
   * An **Elastic Load Balancer (ELB)** in AWS automatically distributes incoming traffic across multiple targets, such as EC2 instances, containers, or IP addresses, to ensure high availability and fault tolerance.  

#### Key Roles:
- **Traffic Distribution**: Balances traffic across multiple instances or availability zones.  
- **Health Monitoring**: Detects unhealthy targets and routes traffic only to healthy ones.  
- **Scalability**: Supports auto-scaling by adapting to changing traffic loads.  
- **SSL Termination**: Handles SSL/TLS encryption for secure communication.  

#### Example:
In a web application, ELB distributes user requests across multiple EC2 instances, ensuring consistent performance and high availability.


4. **DevOps**: Describe the differences between development and production environments.

| **Aspect**             | **Development Environment**                      | **Production Environment**              |  
|-------------------------|--------------------------------------------------|-----------------------------------------|  
| **Purpose**             | Used for building, testing, and debugging code. | Hosts the live application for end-users. |  
| **Stability**           | Can be unstable due to ongoing changes.         | Must be highly stable and reliable.      |  
| **Access**              | Accessible to developers and testers.           | Accessible to end-users.                 |  
| **Data**                | Uses dummy or test data.                        | Uses real user data.                     |  
| **Monitoring**          | Focuses on debugging and profiling.             | Focuses on performance and uptime.       |  

#### Example:
Developers may work in a development environment with debugging tools enabled, while end-users access a highly optimized and secure production environment.


5. **Tools & Technology**: Use Docker Compose to start multiple containers.
   * Docker Compose is a tool for defining and managing multi-container Docker applications using a YAML file.  

#### Steps to Start Multiple Containers:
1. **Create a `docker-compose.yml` file**:
   ```yaml
   version: '3.8'
   services:
     web:
       image: nginx:latest
       ports:
         - "80:80"
     database:
       image: mysql:latest
       environment:
         MYSQL_ROOT_PASSWORD: rootpassword
   ```  
2. **Start the containers**:
   ```bash
   docker-compose up
   ```
3. **Stop the containers**:
   ```bash
   docker-compose down
   ```

This setup starts an Nginx web server and a MySQL database together.


6. **Scenario**: How would you isolate development and production environments in the cloud?





