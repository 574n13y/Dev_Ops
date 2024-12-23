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
   1. **Build Stage**:
   - **Purpose**: Converts source code into executable artifacts.
   - **Processes**:
    - Compiling code.
    - Resolving dependencies.
    - Packaging into formats like `.jar`, `.war`, or `.docker`.
   - **Tools**: Maven, Gradle, Docker.

   2. **Test Stage**:
   - **Purpose**: Ensures code quality and functionality through automated tests.
   - **Processes**:
    - Unit testing.
    - Integration testing.
    - Performance and security testing.
   - **Tools**: JUnit, Selenium, JMeter.

   3. **Deploy Stage**:
   - **Purpose**: Releases the built and tested application to production or staging environments.
   - **Processes**:
    - Infrastructure provisioning.
    - Deploying artifacts to servers or containers.
    - Configuring monitoring tools.
   - **Tools**: Terraform, Ansible, Kubernetes.


5. **Tools & Technology**: Set up a Jenkins job to deploy code to an S3 bucket.
   ##### **Steps**:
   1. **Install Jenkins Plugins**:
    - Install the **AWS CLI** and **S3 Publisher** plugins.

   2. **Create a New Jenkins Job**:
    - Go to Jenkins dashboard > **New Item** > **Freestyle Project**.

   3. **Configure Source Code Management**:
    - Use Git to pull code from the repository.

   4. **Add Build Steps**:
    - Install AWS CLI on the Jenkins server.
    - Add a build step to deploy code to an S3 bucket:
     ```bash
     aws s3 cp /path/to/your/files s3://your-bucket-name/ --recursive
     ```

  5. **Trigger the Job**:
    - Trigger manually or use a webhook for automated deployment.


6. **Scenario**: Your team wants to distribute content globally. What solutions would you suggest?
   ##### **Solution**: Use a **Content Delivery Network (CDN)** like **Amazon CloudFront**.

   **Benefits**:
    1. **Global Reach**: Delivers content from edge locations closest to users, reducing latency.
    2. **Scalability**: Handles traffic spikes without impacting performance.
    3. **Cost Efficiency**: Reduces load on the origin server, lowering operational costs.
    4. **Security**: Protects content with AWS Shield and enables secure HTTPS delivery.

   **Implementation**:
    1. Configure an S3 bucket as the origin for CloudFront.
    2. Enable caching for static assets like images, videos, and scripts.
    3. Use custom domain names and SSL certificates for branding and security.


