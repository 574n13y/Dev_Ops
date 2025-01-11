# Day 58


1. **Linux**: Use `cron` to automate a daily backup.
   - The `cron` utility in Linux is used to schedule tasks. To automate a daily backup, follow these steps:
 
    1. **Create a Backup Script**:
   ```bash
   #!/bin/bash
   tar -czf /backup/my_backup_$(date +%Y-%m-%d).tar.gz /path/to/files
   ```
   Save this script as `backup.sh` and make it executable:
   ```bash
   chmod +x backup.sh
   ```
  
    2. **Schedule the Script Using `cron`**:
   Open the `crontab` editor:
   ```bash
   crontab -e
   ```
   Add the following line to schedule the backup at 2 AM daily:
   ```bash
   0 2 * * * /path/to/backup.sh
   ```
   Save and exit. The task will now run daily at the specified time.


2. **Networking**: Describe NAT Gateway and its use cases in cloud environments.
   - A **NAT Gateway (Network Address Translation Gateway)** allows instances in a private subnet to access the internet while preventing incoming traffic from the internet.

   **Use Cases**:
    1. **Private Subnet Internet Access**: Instances in private subnets can download updates or connect to external APIs.
    2. **Secure Architectures**: Protects private instances from direct exposure to the internet.
    3. **Cost Efficiency**: A managed NAT Gateway is easier to maintain compared to custom NAT instances.


3. **Cloud Computing**: Explain AWS CloudFormation and its advantages.
   - AWS **CloudFormation** is an Infrastructure as Code (IaC) service that allows you to model, provision, and manage AWS resources using declarative JSON or YAML templates.

   **Advantages**:
    - **Automation**: Automates the provisioning of resources, reducing manual effort.
    - **Repeatability**: Ensures consistent infrastructure deployments across environments.
    - **Version Control**: Templates can be stored in source control, enabling tracking and rollbacks.
    - **Dependency Management**: Automatically handles dependencies between resources.
    - **Cost Management**: Enables better tracking of resource usage through stack templates.


4. **DevOps**: Compare manual provisioning vs. IaC.
   
   | **Aspect**             | **Manual Provisioning**                       | **Infrastructure as Code (IaC)**             |
   |------------------------|-----------------------------------------------|----------------------------------------------|
   | **Process**            | Resources are provisioned through GUIs or CLI commands. | Resources are defined using code (e.g., Terraform, CloudFormation). |
   | **Consistency**        | Prone to human error; inconsistent results.   | Ensures consistency and repeatability.       |
   | **Scalability**        | Difficult to scale due to manual steps.       | Highly scalable through automated scripts.   |
   | **Version Control**    | No version control for infrastructure changes.| Supports versioning through source control.  |
   | **Speed**              | Time-consuming and error-prone.              | Fast and automated.                          |
   | **Collaboration**      | Limited; difficult to share configurations.   | Easy collaboration via code repositories.    |


5. **Tools & Technology**: Deploy a CloudFormation stack to create a VPC.
   - **Step-by-Step Guide**:
    
    1. **Prepare the CloudFormation Template**:
   ```yaml
   AWSTemplateFormatVersion: "2010-09-09"
   Resources:
     MyVPC:
       Type: "AWS::EC2::VPC"
       Properties:
         CidrBlock: "10.0.0.0/16"
         EnableDnsSupport: true
         EnableDnsHostnames: true
         Tags:
           - Key: "Name"
             Value: "MyVPC"
   ```
    
    2. **Deploy the Stack**:
    - Save the file as `vpc-template.yaml`.
    - Use the AWS Management Console or CLI to deploy:
     ```bash
     aws cloudformation create-stack --stack-name MyVPCStack --template-body file://vpc-template.yaml
     ```
    
    3. **Verify the Deployment**:
    - Use the AWS Console to confirm the VPC is created.
    - List the stack using the CLI:
     ```bash
     aws cloudformation describe-stacks --stack-name MyVPCStack
     ```


6. **Scenario**: Your infrastructure needs a repeatable deployment setup. How would you achieve this?

