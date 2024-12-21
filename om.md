# Day 44

1. **Linux**: Practice with `ln` to create hard and symbolic links.
   - **Hard Links**:  
    - A hard link is a direct reference to the physical data on disk.
    - Deleting the original file doesn’t affect the hard link.

   **Command**:
     ```bash
     ln file1.txt hardlink_file1.txt
     ```

   **Verify**:
     ```bash
     ls -li
     ```

   - **Symbolic Links (Soft Links)**:  
    - A soft link is a pointer to the original file. It breaks if the original file is deleted.

   **Command**:
     ```bash
     ln -s file1.txt symlink_file1.txt
     ```

   **Verify**:
     ```bash
     ls -l
     ```


2. **Networking**: What is a default gateway, and why is it necessary?
   - **Default Gateway**:  
    - A router or network node that routes traffic from a local network to other networks or the internet.  
    - It serves as the access point for devices to communicate with external networks.  

   - **Why Necessary?**:  
    - Without a default gateway, devices on a local network would be unable to send or receive data outside their network.  

  **Example**:
    ```plaintext
    Device IP: 192.168.1.10
    Subnet Mask: 255.255.255.0
    Default Gateway: 192.168.1.1
    ```

    Here, 192.168.1.1 routes traffic to external networks like the internet.


3. **Cloud Computing**: Discuss the purpose of AWS Auto Scaling.
   - **What is Auto Scaling?**
    - Automatically adjusts the number of EC2 instances (or other resources) in response to traffic demands.

   - **Benefits**:
    1. **Cost Optimization**: Only pay for resources when needed.
    2. **High Availability**: Ensures applications remain available under heavy traffic.
    3. **Scalability**: Handles sudden traffic spikes without manual intervention.

   - **Components**:
    1. **Auto Scaling Groups (ASG)**: A collection of EC2 instances managed together.
    2. **Launch Template/Configuration**: Defines instance details like AMI, instance type, etc.
    3. **Scaling Policies**: Rules that define when to scale in or out.


4. **DevOps**: Define continuous monitoring and its role in DevOps.
   - **Continuous Monitoring (CM):**
    - The practice of observing applications, infrastructure, and services in real time to identify and resolve issues promptly.

   - **Role in DevOps**:
    1. **Proactive Issue Detection**: Identifies problems before they impact users.
    2. **Enhanced Collaboration**: Provides feedback to development, QA, and operations teams.
    3. **Improved Reliability**: Ensures systems meet SLAs (Service Level Agreements).

   - **Tools**:
    - Prometheus, Grafana, ELK Stack (Elasticsearch, Logstash, Kibana), Datadog.


5. **Tools & Technology**: Set up monitoring in Grafana with a basic dashboard.
   * **Steps**:
   1. **Install Prometheus and Grafana**:
    - Follow the official documentation for installation on your platform.

   2. **Configure Prometheus as a Data Source**:
    - Access Grafana at `http://<grafana-server>:3000`.
    - Go to **Configuration → Data Sources → Add Data Source**.
    - Select **Prometheus** and provide the Prometheus server URL (e.g., `http://localhost:9090`).

   3. **Create a Dashboard**:
    - Go to **Dashboards → New Dashboard → Add New Panel**.
    - Add a query (e.g., `rate(http_requests_total[5m])`).
    - Save the dashboard.


6. **Scenario**: An application needs real-time monitoring. How would you set it up?


