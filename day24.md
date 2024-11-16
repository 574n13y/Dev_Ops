# Day 24

---

1. **Linux**: Move files using the `mv` command.
  - The `mv` command in Linux is used to move or rename files and directories.  
    **Syntax**:  
    ```bash
    mv [options] source destination
    ```

    **Examples**:
   - Move a file:  
     ```bash
     mv file1.txt /home/user/documents/
     ```
   - Rename a file:  
     ```bash
     mv oldname.txt newname.txt
     ```
   - Move and overwrite without prompt:  
     ```bash
     mv -f file1.txt /home/user/documents/
     ```
   - Prompt before overwriting:  
     ```bash
     mv -i file1.txt /home/user/documents/
     ```


2. **Networking**: Explain the purpose of the `traceroute` command.
   
   - The `traceroute` command is a network diagnostic tool used to trace the path packets take from the source to the destination.

    **Purpose**:
   1. Identify intermediate routers/hops between two systems.
   2. Diagnose connectivity issues or identify bottlenecks.
   3. Understand network latency and routing.

   **Syntax**:
   ```bash
   traceroute [options] hostname_or_IP
   ```

   **Example**:
   ```bash
   traceroute google.com
   ```

   **Output**:
    The output displays the hops (routers) along the path and the response time for each hop.


3. **Cloud Computing**: Describe cloud regions and availability zones in AWS.
   - **Regions**:
    - Geographically isolated locations worldwide (e.g., `us-east-1`, `eu-west-1`).
    - Each region contains multiple availability zones.
    - Data transfer across regions incurs additional costs.

   - **Availability Zones (AZs)**:
    - Data centers within a region, isolated but interconnected.
    - Provide fault tolerance and high availability.
    - Examples: `us-east-1a`, `us-east-1b`.

   **Purpose**:
    - Regions ensure global coverage.
    - AZs enhance reliability and scalability by enabling redundancy.


4. **DevOps**: Explain the concept of Infrastructure as Code (IaC).
    **Concept**:
    Infrastructure as Code (IaC) is the practice of defining and managing infrastructure (servers, networks, etc.) using code. It enables automation, repeatability, and version control.

    **Key Benefits**:
   1. Consistency: Ensures environments are identical across deployments.
   2. Automation: Eliminates manual configuration errors.
   3. Scalability: Quickly deploy infrastructure at scale.

   **Popular Tools**:
   - **Terraform**: Cloud-agnostic IaC tool.
   - **AWS CloudFormation**: Manages AWS resources.
   - **Ansible**: Automates configuration and deployment.

   **Example**:
   A Terraform script to deploy an AWS EC2 instance:
   ```hcl
   resource "aws_instance" "example" {
     ami           = "ami-12345678"
     instance_type = "t2.micro"
    }
   ```


5. **Tools & Technology**: Install the AWS CLI and configure a user.
   **Install AWS CLI**:
   1. **On Linux**:
    ```bash
     curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
     unzip awscliv2.zip
     sudo ./aws/install
    ```

   2. **On macOS**:
    ```bash
     brew install awscli
    ```

   3. **On Windows**:
    - Download the installer from [AWS CLI Downloads](https://aws.amazon.com/cli/).

    **Configure AWS CLI**:
   1. Run the configuration command:
     ```bash
     aws configure
     ```
   2. Enter the following details:
    - Access Key ID
    - Secret Access Key
    - Default Region (e.g., `us-east-1`)
    - Output Format (`json`, `table`, or `text`)

    **Verify Installation**:
   ```bash
   aws --version
   ```


6. **Scenario**: A server needs to run scripts at specific intervals. How would you set this up?

