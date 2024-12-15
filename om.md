# Day 39

1. **Linux**: Use `sed` to edit text in files programmatically.
    -   `sed` (stream editor) is used to perform text transformations or edits on files programmatically.  

     **Examples:**  
   - Replace text:  
     ```bash
     sed 's/old_text/new_text/' file.txt
     ```  
      Replaces the first occurrence of `old_text` with `new_text` in each line.

   - Replace globally:  
     ```bash
     sed 's/old_text/new_text/g' file.txt
     ```  
      Replaces all occurrences of `old_text` with `new_text` in each line.

   - In-place edits:  
     ```bash
     sed -i 's/old_text/new_text/g' file.txt
     ```  
      Modifies the file directly without creating a new one.

   - Delete lines containing a pattern:  
     ```bash
     sed '/pattern/d' file.txt
     ```

2. **Networking**: What is DNS? Explain how it works.
    * **DNS (Domain Name System):**  
    DNS is a hierarchical system that translates human-readable domain names (e.g., `example.com`) into IP addresses (e.g., `192.0.2.1`), enabling computers to locate resources over a network.  

   * **How It Works:**  
    1. **User Query:** The user enters a domain name in their browser.  
    2. **DNS Resolver:** The request is sent to a DNS resolver, often managed by the ISP.  
    3. **Root Servers:** If the resolver doesn't know the IP address, it queries a root server, which directs it to the appropriate **TLD (Top-Level Domain)** server (e.g., `.com`, `.org`).  
    4. **Authoritative DNS Server:** The TLD server provides the location of the authoritative DNS server for the domain, which returns the IP address.  
    5. **Caching:** The resolver caches the result for faster future access.  
    6. **Response:** The resolver returns the IP address to the browser, which establishes a connection to the web server.  


3. **Cloud Computing**: Describe the concept of IAM (Identity and Access Management) in AWS.
   * **AWS IAM:**  
AWS IAM is a service that enables secure access control for AWS resources by managing users, roles, and permissions.

   **Core Concepts:**  
   - **Users:** Individual accounts for people or applications.  
   - **Groups:** Collections of users that share the same permissions.  
   - **Roles:** Temporary access permissions assigned to users or services for specific tasks.  
   - **Policies:** JSON-based documents defining permissions for users, groups, and roles.  

   **Best Practices:**  
   - Enforce the principle of least privilege.  
   - Use MFA (Multi-Factor Authentication) for sensitive accounts.  
   - Rotate access keys and credentials regularly.  
   - Monitor access using AWS CloudTrail.  


4. **DevOps**: Define CI/CD pipelines and list their components.
   * **CI/CD (Continuous Integration/Continuous Deployment):**  
CI/CD pipelines automate the process of building, testing, and deploying code to production.

   **Components of a CI/CD Pipeline:**  
   1. **Source Stage:** Monitors version control systems (e.g., Git) for code commits.  
   2. **Build Stage:** Compiles code and packages artifacts.  
   3. **Test Stage:** Runs automated tests (unit, integration, and end-to-end).  
   4. **Deploy Stage:** Deploys the application to staging, testing, or production environments.  
   5. **Monitoring Stage:** Observes application performance and detects deployment issues.  

**Benefits:**  
- Faster delivery cycles.  
- Early bug detection.  
- Automated deployments reduce human error.  

5. **Tools & Technology**: Set up a basic pipeline in Jenkins to build and test code.
   * **Steps to Create a Jenkins Pipeline:**  

   1. **Install Jenkins:**  
   - Download and install Jenkins from [jenkins.io](https://jenkins.io).  
   - Configure Jenkins with required plugins (e.g., Git, Pipeline).  

   2. **Create a New Pipeline Job:**  
   - Navigate to Jenkins dashboard → **New Item** → Select **Pipeline**.  

   3. **Define the Pipeline Script:**  
   - Example Script for a Build and Test Pipeline:
     ```groovy
     pipeline {
         agent any
         stages {
             stage('Clone Repository') {
                 steps {
                     git 'https://github.com/your-repo.git'
                 }
             }
             stage('Build') {
                 steps {
                     sh './build.sh'
                 }
             }
             stage('Test') {
                 steps {
                     sh './test.sh'
                 }
             }
         }
     }
     ```

   4. **Run the Pipeline:**  
   - Save and build the job to execute the pipeline.



6. **Scenario**: A team needs automatic testing for every code commit. How would you set it up?


