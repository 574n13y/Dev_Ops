# Day 61


1. **Linux**: Experiment with `netstat` for network diagnostics.
   - The `netstat` command is a powerful tool to analyze network connections, routing tables, and port usage.  
    - **Basic Usage**:  
      ```bash
      netstat -a  # Displays all connections and listening ports  
      netstat -t  # Shows TCP connections  
      netstat -u  # Shows UDP connections  
      netstat -l  # Lists listening ports  
      netstat -r  # Displays the kernel routing table  
      netstat -s  # Displays network statistics  
      ```

   - **Common Scenarios**:  
    - Check for open ports and their associated services.
    - Diagnose network performance issues.
    - Identify suspicious network activity.


2. **Networking**: Explain IP address classes.
   - IP addresses are categorized into five classes (A to E) based on their range and purpose.  

   | **Class** | **Range**                | **Default Subnet Mask** | **Usage**                      |  
   |-----------|--------------------------|--------------------------|--------------------------------|  
   | **A**     | 0.0.0.0 - 126.255.255.255 | 255.0.0.0                | Large networks (e.g., ISPs).  |  
   | **B**     | 128.0.0.0 - 191.255.255.255 | 255.255.0.0              | Medium-sized networks.        |  
   | **C**     | 192.0.0.0 - 223.255.255.255 | 255.255.255.0            | Small networks (e.g., LANs).  |  
   | **D**     | 224.0.0.0 - 239.255.255.255 | N/A                      | Multicasting.                 |  
   | **E**     | 240.0.0.0 - 255.255.255.255 | N/A                      | Reserved for future use.      |  
   
   * 127.0.0.1 is loopback address


3. **Cloud Computing**: Discuss how S3 storage tiers work.
   - Amazon S3 offers different storage tiers to optimize costs based on data access patterns:  
   
   1. **S3 Standard**:  
    - High durability and availability.  
    - Best for frequently accessed data.  
   
   2. **S3 Standard-IA (Infrequent Access)**:  
    - Lower cost for infrequently accessed data.  
    - Retrieval fees apply.  
   
   3. **S3 One Zone-IA**:  
    - Stores data in a single availability zone.  
    - Cheaper than Standard-IA but less durable.  
   
   4. **S3 Intelligent-Tiering**:  
    - Automatically moves data between tiers based on usage patterns.  
    - No retrieval fees for access pattern changes.  
   
   5. **S3 Glacier**:  
    - Low-cost storage for long-term archiving.  
    - Retrieval times range from minutes to hours.  
   
   6. **S3 Glacier Deep Archive**:  
    - Lowest-cost storage for data rarely accessed.  
    - Retrieval times are longer (up to 12 hours).  


4. **DevOps**: Define automated testing and its importance in CI/CD.
   * **Automated Testing** involves running predefined test scripts automatically to verify that the application behaves as expected.  

   - **Types of Automated Tests**:  
    - **Unit Tests**: Validate individual functions or modules.  
    - **Integration Tests**: Ensure different components work together.  
    - **End-to-End Tests**: Simulate real-world user scenarios.  

   - **Importance in CI/CD**:  
    - Detects bugs early in the development cycle.  
    - Reduces manual testing efforts.  
    - Ensures consistent testing after every code change.  
    - Enables faster feedback loops for developers.  
    - Improves overall software quality and reliability.  


5. **Tools & Technology**: Set up a simple testing pipeline in Jenkins.
    1. **Install Jenkins**:  
    - Download and set up Jenkins on your system or server.  
    - Install necessary plugins, such as Git and Pipeline.  
   
    2. **Create a New Pipeline Job**:  
    - Go to Jenkins dashboard → New Item → Pipeline.  
   
    3. **Define a Pipeline Script**:  
       Example for a Python project with unit tests:  
       ```groovy  
       pipeline {  
           agent any  
             stages {  
               stage('Clone Repository') {  
                   steps {  
                      git 'https://github.com/your-repo.git'  
                  }  
              }   
             stage('Install Dependencies') {  
                 steps {  
                       sh 'pip install -r requirements.txt'  
                 }  
              }  
              stage('Run Tests') {  
                 steps {  
                     sh 'pytest --junitxml=test-results.xml'  
                 }  
             }  
         }  
          post {  
              always {  
                  junit 'test-results.xml'  
                }  
           }  
        }  
       ```  
   
    4. **Run the Job**:  
    - Save the pipeline and trigger the build.  
    - Jenkins will execute the steps and display results.  


6. **Scenario**: You need to automate unit tests for every code push. How would you do it?
   - To automate unit tests for every code push:  
    
    1. **Set Up a CI/CD Tool**:  
    - Use tools like Jenkins, GitHub Actions, or GitLab CI/CD.  
    
    2. **Integrate with Version Control**:  
    - Connect the CI/CD tool to your Git repository.  
    - Configure triggers for builds on every push or pull request.  
    
    3. **Define a Build Pipeline**:  
    - Steps include cloning the repository, installing dependencies, running unit tests, and reporting results.  
    
    4. **Run Tests in Parallel**:  
    - Leverage parallelization to speed up testing for large codebases.  
    
    5. **Notify the Team**:  
    - Send automated notifications (e.g., Slack, email) with build/test results.  
    
    6. **Use Test Reports**:  
    - Generate and store test reports for tracking and debugging.  

