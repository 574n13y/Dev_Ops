# Day 84


1. **Linux**: Set up SSH key-based authentication for remote access.
   - SSH key-based authentication improves security by **eliminating the need for passwords** while ensuring secure remote access.  
   
    * **Steps to Set Up SSH Key-Based Authentication:**  
    1. **Generate an SSH Key Pair (on local machine):**  
       ```bash
       ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
       ```  
    - Saves the private key (`id_rsa`) and public key (`id_rsa.pub`) in `~/.ssh/`  
    2. **Copy the Public Key to the Remote Server:**  
       ```bash
       ssh-copy-id user@remote-server
       ```  
       Or manually add the public key to `~/.ssh/authorized_keys` on the remote machine.  
    3. **Set Proper Permissions:**  
       ```bash
       chmod 600 ~/.ssh/authorized_keys
       chmod 700 ~/.ssh
       ```  
    4. **Disable Password Authentication (optional, for better security):**  
       Edit `/etc/ssh/sshd_config`:  
       ```bash
       PasswordAuthentication no
       PubkeyAuthentication yes
       ```  
       Restart SSH:  
       ```bash
       sudo systemctl restart sshd
       ```  


2. **Networking**: What is Anycast, and how does it work in routing?
   * **Anycast** is a network addressing method where **multiple servers share the same IP address**, and requests are **routed to the nearest** or most optimal server.  

   * **How It Works:**  
    - The same IP address is announced from multiple locations.  
    - Routers use **BGP (Border Gateway Protocol)** to determine the closest server.  
    - Requests are **automatically routed** to the nearest available instance.  

   * **Use Cases:**  
    - **CDNs (Content Delivery Networks)**: Cloudflare, AWS CloudFront.  
    - **DNS Resilience**: Google Public DNS (`8.8.8.8`), OpenDNS.  
    - **DDoS Mitigation**: Traffic is distributed, reducing attack impact.  


3. **Cloud Computing**: Define Amazon ECS and how it differs from EKS.
   - ### **3. Cloud Computing: Define Amazon ECS and How It Differs from EKS**  
Amazon ECS (Elastic Container Service) and EKS (Elastic Kubernetes Service) are **container orchestration services**, but they serve different use cases.  

    | Feature     | Amazon ECS | Amazon EKS |
    |------------|-----------|------------|
    | **Orchestration Engine** | AWS native (proprietary) | Kubernetes |
    | **Complexity** | Easier to manage | More complex |
    | **Control Plane** | Fully managed by AWS | Requires Kubernetes cluster setup |
    | **Networking** | Integrated with AWS networking | Uses Kubernetes networking (CNI) |
    | **Scaling** | Autoscaling with Fargate or EC2 | Kubernetes native scaling |

   * **When to Use ECS?**  
   - If you **don’t need Kubernetes** and prefer AWS-native integration.  
   - If you want **simpler** deployment and **less operational overhead**.  

   * **When to Use EKS?**  
   - If you **require Kubernetes** and multi-cloud portability.  
   - If you need **greater flexibility** in container orchestration.  


4. **DevOps**: Explain the role of observability in system reliability.
  * **Observability** provides deep system insights to detect, diagnose, and prevent failures. It consists of three pillars:  
   1. **Metrics**: Numeric values representing system health (CPU usage, memory, request latency).  
   2. **Logs**: Event records for troubleshooting (application logs, system logs).  
   3. **Traces**: End-to-end request tracking across microservices (AWS X-Ray, Jaeger).  

  * **How Observability Improves Reliability:**  
   - **Proactive Monitoring**: Detect issues before they impact users.  
   - **Root Cause Analysis**: Identify exact failure points.  
   - **Performance Optimization**: Fine-tune system performance.  
   - **Faster Incident Response**: Enables quick diagnosis and resolution.  

   * **Tools:** AWS CloudWatch, Prometheus, Grafana, Datadog, OpenTelemetry.  


5. **Tools & Technology**: Launch a simple task on Amazon ECS.
    * Amazon ECS allows running containers without managing infrastructure.  
    
    - **Steps to Launch a Simple Task on ECS (Fargate Mode)**  
    
    1. **Create an ECS Cluster**  
       ```bash
       aws ecs create-cluster --cluster-name my-ecs-cluster
       ```  
    
    2. **Register a Task Definition (JSON example for Nginx container):**  
       ```json
       {
         "family": "nginx-task",
         "networkMode": "awsvpc",
         "containerDefinitions": [
           {
             "name": "nginx",
             "image": "nginx:latest",
             "memory": 512,
             "cpu": 256,
             "essential": true
           }
         ],
         "requiresCompatibilities": ["FARGATE"],
         "cpu": "256",
         "memory": "512"
       }
       ```  
       Register it:  
       ```bash
       aws ecs register-task-definition --cli-input-json file://task-def.json
       ```  
    
    3. **Run the ECS Task:**  
       ```bash
       aws ecs run-task --cluster my-ecs-cluster --task-definition nginx-task --launch-type FARGATE
       ```  
    
    4. **Check Task Status:**  
       ```bash
       aws ecs list-tasks --cluster my-ecs-cluster
       ```  


6. **Scenario**: You need to deploy containerized applications without Kubernetes. What AWS service would you use?
   * If Kubernetes is **not required**, the best AWS service for deploying containerized applications is **Amazon ECS with AWS Fargate**.  

   * **Why Choose ECS + Fargate?**  
    - **No need to manage servers** (fully serverless).  
    - **Deep AWS integration** (IAM, CloudWatch, ALB).  
    - **Scalability**: Auto-scales based on demand.  
    - **Cost-efficient**: Pay only for running containers.  

   * **Alternative Approaches:**  
    1. **Amazon Lightsail Containers**: Simplified container service for small apps.  
    2. **Elastic Beanstalk for Docker**: Managed PaaS for Dockerized applications.  
    3. **EC2 with Docker**: For full control over container orchestration.  



