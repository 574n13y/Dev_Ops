# Day 82 


1. **Linux**: Use `rsyslog` for centralized logging.
   - `rsyslog` is a powerful logging tool that can be used to collect logs from multiple sources and send them to a centralized server.  

   * **Steps to configure centralized logging using `rsyslog`:**  
    1. **Install `rsyslog` on both client and server:**  
       ```bash
       sudo apt update && sudo apt install -y rsyslog
       ```  
    
    2. **Enable remote logging on the server (`/etc/rsyslog.conf` or `/etc/rsyslog.d/50-default.conf`):**  
       ```bash
       $ModLoad imtcp  
       $InputTCPServerRun 514  
       ```  
    
    3. **Configure clients to send logs to the server (`/etc/rsyslog.conf`):**  
       ```bash
       *.* @logserver_ip:514
       ```  
    
    4. **Restart the `rsyslog` service:**  
       ```bash
       sudo systemctl restart rsyslog
       ```  
    
    5. **Verify logs on the server (`/var/log/syslog` or `/var/log/messages`).**  


2. **Networking**: Explain SSL offloading and its benefits.
   * **SSL offloading** is the process of moving SSL/TLS encryption and decryption tasks from web servers to a separate device like a **load balancer** or **proxy server**.  

   * **Benefits of SSL Offloading:**  
    - **Performance improvement**: Reduces CPU load on web servers.  
    - **Simplified certificate management**: Certificates are managed in one place.  
    - **Faster connections**: Reduces latency for encrypted connections.  
    - **Enhanced security**: Centralized control over encryption policies.  

     Common SSL offloading services include **AWS ELB (Elastic Load Balancer), Nginx, F5 Big-IP, and HAProxy**.  


3. **Cloud Computing**: Describe AWS S3 lifecycle policies for managing object storage.
   - AWS S3 **lifecycle policies** allow you to automatically transition or delete objects based on predefined rules to optimize costs.  

   * **Lifecycle Policy Actions:**  
    - **Transition**: Move objects between storage classes (e.g., Standard → Glacier).  
    - **Expiration**: Automatically delete old objects.  
    - **Noncurrent version expiration**: Manage older versions of objects.  

   * **Example Use Case:**  
    - Move objects to **Glacier** after 30 days.  
    - Delete objects after 365 days.  

   * **Example JSON Policy:**  
     ```json 
     {
       "Rules": [
         {
           "ID": "MoveToGlacier",
           "Prefix": "logs/",
           "Status": "Enabled",
           "Transitions": [
             {
               "Days": 30,
               "StorageClass": "GLACIER"
             }
           ],
           "Expiration": {
             "Days": 365
           }
         }
       ]
     }
     ```  


4. **DevOps**: What is the difference between logging and monitoring?
   
     | Feature      | Logging  | Monitoring |
     |-------------|---------|------------|
     | **Purpose**  | Stores event data | Observes system health |
     | **Data Type** | Raw logs (text, JSON) | Metrics, trends |
     | **Usage** | Troubleshooting | Performance optimization |
     | **Examples** | System logs, application logs | CPU usage, response time |
     | **Tools** | ELK Stack, Fluentd | Prometheus, Grafana |

   * **Key takeaway:**  
    - **Logging** helps debug issues by capturing events.  
    - **Monitoring** provides real-time system insights for proactive management.  


5. **Tools & Technology**: Configure an S3 lifecycle policy to transition objects to Glacier.
   * To configure an **S3 lifecycle policy**:  

   * **Step 1: Open AWS S3 console**  
    1. Navigate to **S3 → Your bucket**  
    
    2. Click **Management → Lifecycle Rules**  
    
    3. **Create a new lifecycle rule**  
    - Rule Name: `MoveToGlacier`  
    - Select **"Transition current versions of objects"**  
    - Move to **Glacier after 30 days**  
    - Enable expiration (optional)  

   * **Step 2: Apply JSON Policy (Terraform Example)**  
     ```hcl
     resource "aws_s3_bucket_lifecycle_configuration" "example" {
       bucket = "my-example-bucket"
     
       rule {
         id     = "MoveToGlacier"
         status = "Enabled"
     
         transition {
           days          = 30
           storage_class = "GLACIER"
         }
     
         expiration {
           days = 365
         }
       }
     }
     ```  
   * **Apply using Terraform:**  
     ```bash
     terraform apply
     ```  


6. **Scenario**: You need to reduce costs for storing old files without deleting them. How would you configure this?
    * To reduce storage costs while **retaining** data:  
    1. **Enable S3 lifecycle policies** to move infrequently accessed files to **S3 Glacier** after a set period.  
    2. **Use Intelligent-Tiering** for automatic storage cost optimization.  
    3. **Compress files** before archiving to reduce size.  
    4. **Delete old non-essential versions** using **versioning lifecycle policies**.  

 



