# Day 75


1. **Linux**: Manage services using systemctl (e.g., start, stop, enable services).
   - `systemctl` is a command-line utility for managing system services and processes on Linux systems using **systemd**. Here are common tasks:
 
    - **Start a service:**  
      ```bash
      sudo systemctl start <service_name>
      ```
      Example: `sudo systemctl start apache2`
   
    - **Stop a service:**  
      ```bash
      sudo systemctl stop <service_name>
      ```
   
    - **Restart a service:**  
      ```bash
      sudo systemctl restart <service_name>
      ```
    
    - **Enable a service to start on boot:**  
      ```bash
      sudo systemctl enable <service_name>
       ```
    
    - **Disable a service from starting on boot:**  
      ```bash
      sudo systemctl disable <service_name>
      ```
    
    - **Check the status of a service:**  
      ```bash
      systemctl status <service_name>
      ```


2. **Networking**: What is network latency, and what causes it?
   - **Network latency** is the time it takes for a data packet to travel from the source to the destination and back (round trip). It's often measured in milliseconds (ms). Lower latency indicates better network performance.

   **Causes of Network Latency:**
    1. **Physical Distance:** Greater distance between devices increases latency (e.g., between continents).
    
    2. **Congestion:** High traffic on a network can slow down data transfer.
    
    3. **Routing:** Complex routing with multiple hops adds delay.
    
    4. **Hardware Limitations:** Slow routers, switches, or endpoints can introduce delays.
    
    5. **Packet Loss:** Retransmission of lost packets increases latency.
    
    6. **Network Configuration:** Inefficient settings like mismatched MTU (Maximum Transmission Unit).


3. **Cloud Computing**: Describe Amazon GuardDuty and its purpose.
    - Amazon **GuardDuty** is a managed threat detection service that continuously monitors your AWS environment for malicious or unauthorized activities. It uses machine learning, anomaly detection, and integrated threat intelligence.

   **Purpose:**
    - Detects threats such as account compromise, reconnaissance, and malware.
    
    - Monitors AWS CloudTrail, VPC Flow Logs, and DNS logs.
   
    - Provides actionable security findings that help mitigate risks.
   
    - Integrates with other AWS services like AWS Security Hub and Lambda for automated responses.

 
4. **DevOps**: Explain how to implement security best practices in CI/CD pipelines.
   - To implement security best practices in CI/CD pipelines:
    
    1. **Source Code Security:**
    - Use tools like SonarQube or GitHub Advanced Security to scan for vulnerabilities in code.
    - Enforce secure coding standards and version control (e.g., Git).
    
    2. **Dependency Management:**
    - Use tools like Dependabot or Snyk to monitor and update third-party dependencies.
    
    3. **Static/Dynamic Application Security Testing (SAST/DAST):**
    - Integrate SAST and DAST tools into the pipeline to catch vulnerabilities early.
    
    4. **Secret Management:**
    - Avoid hardcoding secrets; use services like AWS Secrets Manager or HashiCorp Vault.
    
    5. **Access Control:**
    - Limit permissions for pipeline users and roles to follow the principle of least privilege.
    
    6. **Container Security:**
    - Scan container images for vulnerabilities using tools like Trivy or Clair.
    - Use signed images and restrict unsigned ones.
    
    7. **Artifact Integrity:**
    - Use checksums to ensure artifacts (e.g., build outputs) haven’t been tampered with.
    
    8. **Logging and Monitoring:**
    - Monitor pipeline activities using AWS CloudWatch or ELK Stack.


5. **Tools & Technology**: Enable GuardDuty in your AWS account.
    1. **Go to AWS Management Console:**  
    - Navigate to **Amazon GuardDuty**.
    
    2. **Enable GuardDuty:**  
    - Click **Get Started** and enable the service for your account.  
    - Optionally enable GuardDuty in all regions.
    
    3. **Configure Settings:**
    - Set up email notifications for findings via **Amazon SNS**.
    - Enable GuardDuty's integrations with other services like Security Hub.
    
    4. **Monitor Findings:**
    - Go to the **Findings** tab to view detected threats.


6. **Scenario**: Your infrastructure needs active threat detection. How would you set this up?
   - To implement **active threat detection** in your infrastructure:
    
    1. **Enable Amazon GuardDuty:**
    - Follow the steps above to enable GuardDuty.
    
    2. **Enable VPC Traffic Mirroring (Optional):**
    - If deeper packet analysis is needed, mirror traffic to a threat detection tool like AWS NDR partners or open-source tools like Zeek.
    
    3. **Integrate Findings with Security Tools:**
    - Send GuardDuty findings to AWS Security Hub for centralized monitoring.
    - Use Lambda functions to automate responses to high-severity findings (e.g., isolate compromised EC2 instances).
    
    4. **Leverage AWS WAF and Shield:**
    - Use **AWS WAF** for application-layer threat protection.
    - Enable **AWS Shield** for DDoS mitigation.
    
    5. **Continuous Monitoring:**
    - Set up alerts using **CloudWatch Alarms** and SNS.
    - Use a SIEM solution for advanced correlation of GuardDuty findings with other logs. 



