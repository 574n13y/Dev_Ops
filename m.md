# Day 46

1. **Linux**: Use netstat to check network connections.
   * The `netstat` command is used to display active network connections, routing tables, and interface statistics. It’s a powerful tool for diagnosing network issues and monitoring network activity.

   ##### **Examples**:
   - **List all active connections**:
       ```bash
       netstat -a
       ```
   - **Show active TCP connections**:
       ```bash
       netstat -at
       ```
   - **Show listening ports**:
       ```bash
       netstat -l
       ```
   - **Display processes associated with network connections**:
       ```bash
       netstat -tp
       ```
   - **Check statistics for a specific protocol (e.g., TCP)**:
       ```bash
       netstat -st
       ```


2. **Networking**: Describe network latency and its impact on applications.
   * **Network latency** refers to the time it takes for a data packet to travel from the source to the destination and back. It’s often measured in milliseconds (ms). 

   ##### **Impact of Latency on Applications**:
    - **Web Applications**: High latency causes slow page loads, reducing user satisfaction.
    - **Streaming Services**: Increased buffering and degraded quality.
    - **Real-Time Applications**: Critical for applications like online gaming and video conferencing; high latency disrupts user experience.
    - **APIs**: Impacts response times, leading to slower client-server interactions.

   ##### **Common Causes**:
    1. Physical distance between client and server.
    2. Network congestion.
    3. Inefficient routing.
    4. Hardware or software limitations.

   ##### **Mitigation Strategies**:
    - Use Content Delivery Networks (CDNs) to serve content closer to users.
    - Optimize application code and database queries.
    - Implement caching mechanisms.


3. **Cloud Computing**: Explain the role of Amazon CloudFront.
   * **Amazon CloudFront** is a global **Content Delivery Network (CDN)** service designed to accelerate content delivery by caching data at edge locations around the world.

   ##### **Key Features**:
   1. **Low Latency**: Delivers content from edge locations closest to users.
   2. **High Performance**: Caches frequently accessed data to reduce load on origin servers.
   3. **Security**:
    - Integrated with AWS Shield for DDoS protection.
    - Supports HTTPS for secure content delivery.
   4. **Customizable**: Configurable caching behavior and origin server settings.
   5. **Global Reach**: Over 400 points of presence (POPs) worldwide.

   ##### **Use Cases**:
    - Serving static assets like images, CSS, and JavaScript.
    - Streaming video or audio content.
    - Accelerating APIs and dynamic web content.


4. **DevOps**: What’s the difference between build, test, and deploy stages in CI/CD?

5. **Tools & Technology**: Set up a Jenkins job to deploy code to an S3 bucket.

6. **Scenario**: Your team wants to distribute content globally. What solutions would you suggest?


