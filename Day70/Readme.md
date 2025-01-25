# Day 70

1. **Linux**: Explore process management using `pkill` and `killall`.
   - **`pkill`**: Kills processes by matching the process name or other attributes.  
     Example:  
     ```bash
     pkill -f "python"
     ```  
  This command terminates all Python processes.  

   - **`killall`**: Kills all processes with a given name.  
     Example:  
     ```bash
     killall nginx
     ```  
  This command stops all Nginx processes.  

   * Both commands can use additional flags like `-9` (SIGKILL) for forceful termination or `-15` (SIGTERM) for graceful termination.


2. **Networking**: What is MPLS, and why is it used in networking?
   * **MPLS (Multiprotocol Label Switching)** is a data forwarding technique that uses labels to direct packets through a network instead of traditional IP-based routing.  
   
   - **Benefits**:  
    - Improves **speed** by avoiding complex routing table lookups.  
    - Provides **QoS (Quality of Service)** for voice, video, and other latency-sensitive applications.  
    - Ensures **traffic engineering** by optimizing data flows.  

MPLS is commonly used in enterprise networks, ISPs, and WANs to enhance performance and reliability.


3. **Cloud Computing**: Explain how RDS Read Replicas improve performance.
   * **RDS Read Replicas** are copies of your primary database used to offload read-heavy traffic, improving scalability and performance.  

   - **Key Features**:  
    - **Asynchronous Replication**: Changes in the primary DB are asynchronously copied to replicas.  
    - **Read Scaling**: Distribute read workloads across replicas.  
    - **High Availability**: Enhance resilience by promoting a read replica to a primary database during failures.  

Use cases include analytics workloads, reporting, and applications with frequent read operations.


4. **DevOps**: Define Chaos Engineering and its importance.
   * **Chaos Engineering** involves intentionally injecting failures into a system to test its resilience and reliability.  
   
   - **Purpose**: Identify and fix weaknesses in distributed systems before they result in outages.  
   
   - **Examples of Chaos Tests**:  
    - Randomly killing containers or VMs.  
    - Simulating high latency in network traffic.  
    - Testing failover mechanisms by shutting down a database.  

Popular tools include **Chaos Monkey** (Netflix) and **Gremlin**.  


5. **Tools & Technology**: Set up an RDS Read Replica.
    1. **Launch a Primary Database Instance**:  
    - Go to the AWS RDS Console and create a database.  
    
    2. **Create a Read Replica**:  
    - Select the primary DB instance and click **Create Read Replica**.  
    - Choose instance size, availability zone, and other options.  
    
    3. **Modify Application Connection**:  
    - Update the application to use the read replica for read operations (e.g., using the replica endpoint).  


6. **Scenario**: Your database has read-heavy traffic. How would you optimize it?
    1. **Use RDS Read Replicas**:  
    - Offload read queries to replicas while the primary DB handles writes.  
    - Example: Configure a load balancer to distribute read traffic across replicas.  
    
    2. **Enable Query Caching**:  
    - Use database query caching to speed up frequently accessed data.  
    
    3. **Partition Tables**:  
    - Split large tables into smaller partitions to improve query performance.  
    
    4. **Optimize Database Queries**:  
    - Use proper indexing and avoid SELECT *.  
    
    5. **Auto-Scaling Solutions**:  
    - Enable RDS Aurora’s Auto Scaling if applicable.  
    
    6. **Use a CDN**:  
    - Cache data closer to the users if the application serves static or semi-dynamic content.  



