# Day 77


1. **Linux**: Create aliases for frequently used commands in `.bashrc`.
   * **What are Aliases?**
     Aliases are shortcuts for commands or groups of commands in Linux. They simplify repetitive tasks.

   * **Steps to Create Aliases**:
    1. **Open the `.bashrc` File**:
       ```bash
       nano ~/.bashrc
       ```
    
    2. **Add Aliases**:
       Example aliases:
       ```bash
       alias ll='ls -lah'
       alias gs='git status'
       alias grep='grep --color=auto'
       alias update='sudo apt update && sudo apt upgrade -y'
       ```
    
    3. **Apply Changes**:
       Run the following command to apply changes:
       ```bash
       source ~/.bashrc
       ```
    
    4. **Use Aliases**:
       Type the alias (e.g., `ll`) to execute the corresponding command.


2. **Networking**: What is a proxy server, and when would you use one?
   * #### **What is a Proxy Server?**
     A proxy server acts as an intermediary between clients (e.g., web browsers) and servers. It forwards requests from clients to the desired server and relays responses back.

   * **When to Use a Proxy Server?**
    1. **Privacy and Anonymity**:
    - Hides the client’s IP address.
    
    2. **Content Filtering**:
    - Blocks specific websites or content (e.g., in corporate environments).
    
    3. **Performance Optimization**:
    - Caches frequently accessed data to reduce latency.
    
    4. **Security**:
    - Protects internal networks by filtering malicious traffic.
    
    5. **Access Control**:
    - Restricts access to certain resources based on rules.


3. **Cloud Computing**: Discuss Amazon Elasticache and its Redis capabilities.
   * **What is Amazon ElastiCache?**
     Amazon ElastiCache is a managed in-memory data store and cache service for high-speed data access.

   * **Redis Capabilities in ElastiCache**:
    1. **In-Memory Caching**:
    - Stores frequently accessed data for ultra-low latency.
    2. **Data Structures**:
    - Supports lists, sets, hashes, and sorted sets.
    3. **Pub/Sub Messaging**:
    - Enables real-time communication between distributed systems.
    4. **Persistence**:
    - Supports snapshots and backups for data durability.
    5. **Replication and High Availability**:
    - Offers read replicas and multi-AZ deployments.
    6. **Scalability**:
    - Auto-scaling capabilities for handling variable workloads.


4. **DevOps**: Define rollback strategies in deployments.
   * **What is a Rollback Strategy?**
     A rollback strategy is a predefined plan to revert an application to a previous stable state in case of deployment failures.

   * **Common Rollback Strategies**:
    1. **Versioned Deployments**:
    - Maintain multiple application versions and roll back to the previous version if needed.
    
    2. **Blue/Green Deployments**:
    - Switch traffic back to the old environment if the new environment has issues.
    
    3. **Canary Rollbacks**:
    - Gradually roll back changes to minimize impact on users.
    
    4. **Database Rollbacks**:
    - Use database backups or transactional scripts to revert database changes.
    
    5. **Manual Rollbacks**:
    - Redeploy a previous stable build manually (as a last resort).


5. **Tools & Technology**: Deploy a Redis instance using Elasticache.
   * **Steps to Deploy Redis**:
    1. **Login to AWS Management Console**:
    - Navigate to **ElastiCache** service.
    
    2. **Create a Redis Cluster**:
    - Click **Create Cluster**.
    - Select **Redis** as the engine.
    - Configure the following:
     a. Cluster name
     b. Node type (e.g., cache.t2.micro for testing)
     c. Number of replicas (for high availability)
     d. VPC and security groups.
    
    3. **Enable Advanced Options**:
    - Enable **Multi-AZ** for failover.
    - Set up **encryption in transit** for security.
    
    4. **Launch the Cluster**:
    - Review configurations and launch the cluster.
    
    5. **Connect to Redis**:
    - Use the endpoint provided in the ElastiCache dashboard to connect your application.

      Example connection using a Redis client:   
   ```bash
   redis-cli -h <endpoint> -p 6379
   ```


6. **Scenario**: Your application requires caching for fast data retrieval. How would you configure it?
   * **Steps to Configure Caching**:
    1. **Identify Cached Data**:
    - Determine frequently accessed data (e.g., user session data, product details).
    
    2. **Deploy Redis via ElastiCache**:
    - Follow the steps above to set up a Redis instance.
    
    3. **Integrate Redis with the Application**:
    - Use a Redis client library (e.g., `redis-py`, `ioredis`, or `StackExchange.Redis`) to connect the application to Redis.
    
    4. **Set Cache Expiration**:
    - Define expiration policies for cached data to ensure freshness.
    - Example:
      ```python
      redis_client.set("key", "value", ex=3600)  # Expires in 1 hour
      ```
    
    5. **Implement Cache Logic**:
    - Check the cache before querying the database.
    - Example in Python:
      ```python
      value = redis_client.get("key")
      if value is None:
          value = query_database()
          redis_client.set("key", value)
      ```
    
    6. **Monitor Cache Performance**:
    - Use CloudWatch metrics to monitor Redis performance (e.g., cache hits/misses, memory usage).



