# Day 29


1. **Linux**: Describe the `top` command and its usage.
  * The `top` command in Linux is used to monitor system performance in real time. It displays information about processes and system resource usage, such as CPU, memory, and swap. Key features include:  
   - **Process Table:** Shows active processes sorted by CPU usage (default).  
   - **Dynamic Updates:** Data updates every few seconds (customizable).  
   - **Interactive Options:**  
    - `k` to kill a process.  
    - `r` to renice a process.  
    - `P` to sort by CPU usage or `M` for memory.  
   - **Usage Example:**  
     ```bash
     top
     ```
     Press `q` to exit.  


2. **Networking**: Explain ARP and how it works.
  * **ARP** maps an IP address to a physical MAC address on a local network. It operates within the Link Layer of the OSI model.  

   - **How it works:**  
    1. When a device wants to communicate with another device on the same network, it checks its ARP table for the MAC address of the target IP.  
    2. If the MAC address is missing, it sends a broadcast ARP request.  
    3. The device with the requested IP responds with its MAC address.  
    4. The sender updates its ARP table and proceeds with communication.  

   - **Command Example:**  
     ```bash
     arp -a
     ```
  This displays the ARP cache.  


3. **Cloud Computing**: Discuss the benefits of serverless architecture.
  * Serverless architecture allows developers to build and run applications without managing servers. The cloud provider handles the infrastructure.  

   - **Benefits:**  
    - **Cost Efficiency:** Pay only for execution time (e.g., per function invocation).  
    - **Scalability:** Automatically scales up or down based on demand.  
    - **Reduced Operational Overhead:** No server management, patching, or provisioning required.  
    - **Faster Time-to-Market:** Focus solely on application logic.  
    - **Event-Driven:** Ideal for applications with unpredictable workloads or microservices.  


4. **DevOps**: What’s the difference between continuous delivery and continuous deployment?
   
   | **Aspect**             | **Continuous Delivery**                                  | **Continuous Deployment**                                  |
   |-------------------------|---------------------------------------------------------|-----------------------------------------------------------|
   | **Definition**          | Software is always in a deployable state but requires manual approval for release. | Software is automatically released to production without manual intervention. |
   | **Automation Level**    | Automated testing and integration; deployment approval remains manual. | Fully automated, including deployment to production.       |
   | **Use Case**            | Scenarios needing compliance checks or manual oversight. | High-trust environments with minimal risk of failure.      |


5. **Tools & Technology**: Set up a basic Jenkins job.
  * **Steps to Set Up a Basic Jenkins Job:**  
   1. **Install Jenkins:** Ensure Jenkins is installed and accessible via a web interface.  
   2. **Create a New Job:**  
    - Navigate to the Jenkins dashboard.  
    - Click **New Item** and enter a name for the job.  
    - Select **Freestyle Project** and click **OK**.  
   3. **Configure the Job:**  
    - **Source Code Management:** Link the repository (e.g., Git).  
    - **Build Triggers:** Configure triggers, such as polling SCM or a webhook.  
    - **Build Steps:** Add build commands, e.g., a shell script:  
      ```bash
      echo "Building the project"
      ```
    - **Post-Build Actions:** Define steps like archiving artifacts or notifications.  
   4. **Save and Run:** Click **Save** and **Build Now** to trigger the job.  


6. **Scenario**: An application needs automated testing before deployment. How would you set this up?
  * To set up automated testing for an application before deployment:  

   1. **Choose a CI/CD Tool:** Use tools like Jenkins, GitLab CI, or GitHub Actions.  
   2. **Create a Test Pipeline:**  
    - **Fetch Code:** Clone the repository in a pipeline step.  
    - **Install Dependencies:** Use package managers (e.g., `npm install`, `pip install`).  
    - **Run Tests:** Execute automated test scripts (e.g., unit tests, integration tests):  
      ```bash
      pytest tests/
      ```  
   3. **Integrate with Version Control:** Trigger the pipeline on pull requests or code pushes.  
   4. **Configure Notifications:** Alert developers about test results via email or Slack.  
   5. **Deploy on Success:** If all tests pass, deploy the code to staging or production using tools like Terraform or Kubernetes.  



