# Day 43


1. **Linux**: Describe `chmod` in more detail and practice setting file permissions.
   * `chmod` is a Linux command used to change file or directory permissions. Permissions in Linux are defined by **read (r)**, **write (w)**, and **execute (x)** attributes for three categories:  

   1. **Owner**: The user who owns the file.  
   2. **Group**: A group of users who can access the file.  
   3. **Others**: All other users on the system.

   **Permission Syntax**:  
   - **Symbolic**: `chmod u+rwx file` (change permissions for user/owner).  
   - **Numeric**: Permissions are represented as a 3-digit number (e.g., `chmod 755 file`), where each digit defines the permission levels:  
    - **4**: Read  
    - **2**: Write  
    - **1**: Execute  
    - Sum of values determines permissions.  

    | Permission | Numeric | Description         |
    |------------|---------|---------------------|
    | `r--`      | 4       | Read-only          |
    | `rw-`      | 6       | Read and write     |
    | `rwx`      | 7       | Read, write, execute |

   **Example**:
     ```bash
     chmod 644 file  # Owner: rw-, Group: r--, Others: r--
     chmod u+x file  # Add execute permission for the owner
     chmod go-r file # Remove read permission for group and others
     ```


2. **Networking**: Explain the concept of subnets and subnetting.
   * A **subnet** is a logically divided segment of an IP network. Subnetting is the process of dividing a network into smaller, manageable pieces.  

   #### **Why Subnetting?**
   - Improves network performance by reducing broadcast domains.
   - Enhances security by isolating network segments.
   - Efficiently utilizes IP address space.

   **Subnet Mask**: Determines the range of IP addresses in a subnet.  
   - Example: `192.168.1.0/24` (subnet mask: `255.255.255.0`) allows for 256 IPs (254 usable).  

   **CIDR Notation**: Specifies the number of significant bits in the subnet mask.  
   - `/24`: 24 bits for the network, 8 bits for hosts.  

   #### **Subnetting Calculation**:
   1. Determine how many subnets or hosts you need.
   2. Use subnet mask bits to divide the network.
   3. Calculate the network range for each subnet.

    **Example**:
   - Original Network: `192.168.1.0/24`.
   - Subnets: `192.168.1.0/25` (128 IPs), `192.168.1.128/25` (128 IPs).


3. **Cloud Computing**: Describe AWS Route 53 and its use cases.
   * **AWS Route 53** is a scalable and highly available **DNS (Domain Name System)** web service.  

   #### **Key Features**:
    1. **Domain Registration**: Register and manage domain names.
    2. **DNS Routing**: Map domain names to resources like EC2 instances or load balancers.
    3. **Health Checks**: Monitor endpoint health and failover automatically.
    4. **Traffic Management**: Use routing policies for efficient traffic distribution.

   #### **Use Cases**:
    - **Simple DNS Routing**: Map a domain to a single resource (e.g., `www.example.com` → `EC2 instance`).
    - **Load Balancing with Weighted Routing**: Distribute traffic across multiple servers based on weight.
    - **Failover**: Automatically redirect traffic to a healthy endpoint in case of failure.
    - **Geo-location Routing**: Direct users to resources based on their geographic location.


4. **DevOps**: Explain deployment strategies: rolling, blue-green, and canary.
   * Deployment strategies help minimize downtime and risks associated with deploying changes to applications.  

   #### **1. Rolling Deployment**:
    - Gradually update instances with new versions without downtime.
    - Example: Deploy changes to 10% of servers, test, then proceed to the next batch.
    - **Pros**: No downtime, easy rollback.
    - **Cons**: Complexity in managing versions during deployment.

   #### **2. Blue-Green Deployment**:
    - Two environments: **Blue** (current live) and **Green** (new version).  
    - Deploy to Green, then switch traffic from Blue to Green.  
    - **Pros**: Immediate rollback, minimal risk.  
    - **Cons**: Requires duplicate infrastructure.  

   #### **3. Canary Deployment**:
    - Release changes to a small subset of users (e.g., 5%), monitor, then gradually scale.  
    - **Pros**: Safer testing in production.  
    - **Cons**: Requires robust monitoring and routing mechanisms.

   **Recommended Strategy**:  
  For reducing downtime, **Blue-Green Deployment** is ideal as it ensures seamless user experience and immediate rollback capabilities.


5. **Tools & Technology**: Use Jenkins to set up a basic deployment pipeline.
   * **Steps to Create a Basic Deployment Pipeline**:  

   1. **Install Jenkins**: Ensure Jenkins is installed and running.  
   2. **Integrate Source Code**:
    - Add your Git repository to Jenkins.
    - Configure webhooks to trigger builds on new commits.  

   3. **Build Stage**: Compile and package the application.  
    - Example: Use Maven for a Java project:
     ```groovy
     stage('Build') {
         steps {
             sh 'mvn clean install'
         }
     }
     ```

   4. **Test Stage**: Run automated tests.
    - Example: Execute unit tests:
     ```groovy
     stage('Test') {
         steps {
             sh 'mvn test'
         }
     }
     ```

   5. **Deploy Stage**: Deploy to staging or production environments.
    - Example for Docker deployment:
     ```groovy
     stage('Deploy') {
         steps {
             sh 'docker-compose up -d'
         }
     }
     ```

6. **Scenario**: Your team wants to reduce deployment downtime. Which strategy would you recommend?


