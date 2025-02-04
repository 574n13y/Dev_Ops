# Day 81


1. **Linux**: Schedule a recurring backup script with `cron`.
   - To schedule a backup script using `cron`, follow these steps:

   * **Step 1: Create a Backup Script**
     ```sh
     #!/bin/bash
     tar -czf /backup/$(date +\%F)-backup.tar.gz /var/www/html
     ```
    - This script compresses `/var/www/html` and saves it in `/backup/` with a date-based filename.

   * **Step 2: Schedule the Script Using `cron`**
    - Edit the crontab:
     ```sh
     crontab -e
     ```
    - Add the following line to run the backup daily at 2 AM:
     ```sh
     0 2 * * * /path/to/backup-script.sh
     ```


2. **Networking**: What is a VLAN, and how is it used for network segmentation?
   - **VLAN (Virtual Local Area Network)** is a way to segment networks at Layer 2 (Data Link Layer) without needing separate physical switches.
   - It allows different devices on the same physical network to be logically isolated.
   - **Use Cases:**
    - Isolating sensitive systems (e.g., separating finance department traffic from general employee traffic).
    - Improving security and reducing broadcast domain size.


3. **Cloud Computing**: Explain Auto Scaling groups in AWS.
   - **Auto Scaling Groups (ASG)** automatically add or remove EC2 instances based on **scaling policies** (CPU usage, requests per second, etc.).
   - **Key Components:**
    1. **Launch Configuration / Launch Template** – Defines instance settings.
    2. **Desired Capacity** – Number of instances you want running.
    3. **Scaling Policies** – Rules for adding/removing instances.

   **Example:**
    - An ASG with a policy to increase instances if CPU usage exceeds 70%.


4. **DevOps**: Define blue-green deployment and how it ensures zero-downtime deployments.
   - **Blue-Green Deployment** is a strategy where two identical environments exist:
    - **Blue (current production)**
    - **Green (new version)**
   - Steps:
    1. Deploy new version to **Green**.
    2. Test in Green.
    3. Switch traffic from **Blue → Green**.
    4. If an issue occurs, rollback by pointing traffic back to Blue.

   **Benefit:**  
    - **Zero-downtime deployments** since traffic is seamlessly switched.


5. **Tools & Technology**: Set up an Auto Scaling group for an EC2 application.
    * **Step 1: Create a Launch Template**
      ```sh
      aws ec2 create-launch-template --launch-template-name my-template \
          --version-description "Initial version" \
          --launch-template-data file://template.json
      ```
    Example `template.json`:
    ```json
    {
        "ImageId": "ami-12345678",
        "InstanceType": "t3.micro",
        "SecurityGroupIds": ["sg-abc12345"],
        "KeyName": "my-key"
    }
    ```
    
    * **Step 2: Create an Auto Scaling Group**
      ```sh
      aws autoscaling create-auto-scaling-group \
          --auto-scaling-group-name my-asg \
          --launch-template Name=my-template,Version=1 \
          --min-size 1 --max-size 5 --desired-capacity 2 \
          --vpc-zone-identifier "subnet-12345,subnet-67890"
      ```
    
    * **Step 3: Attach a Scaling Policy**
      ```sh
      aws autoscaling put-scaling-policy --auto-scaling-group-name my-asg \
          --policy-name scale-up \
          --scaling-adjustment 1 \
          --adjustment-type ChangeInCapacity
      ```


6. **Scenario**: Your app needs to automatically scale based on traffic. Describe your approach.
   * **Approach**
    
    1. **Set Up an Auto Scaling Group (ASG)**  
    - Use a launch template for instance configuration.
    - Define a **min, max, and desired capacity**.
    
    2. **Attach a Load Balancer**  
    - AWS **Application Load Balancer (ALB)** distributes incoming requests.
    
    3. **Configure Scaling Policies**  
    - **Scale Out:** Add instances when CPU exceeds 70%.
    - **Scale In:** Remove instances when CPU drops below 30%.
    
    4. **Use AWS CloudWatch for Monitoring**  
    - Set alarms to trigger scaling actions.



