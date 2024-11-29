# Day 30


**Day 12**
1. **Linux**: Learn about `ps` and check running processes.
   * The `ps` (process status) command in Linux is used to display information about active processes. It can show a snapshot of the processes running at a specific moment, along with details like process IDs (PIDs), CPU usage, memory usage, and more.

   **Common Options:**
   - `ps` — Shows processes for the current shell.
   - `ps aux` — Displays all processes with detailed information:
    - `a` — All processes with a terminal.
    - `u` — User-oriented format.
    - `x` — Includes processes without a terminal.

   **Example Usage:**
   ```bash
   ps aux | grep process_name
   ```
This searches for a specific process. Use `kill <PID>` to terminate it if needed.


2. **Networking**: What is DHCP, and how does it work?
   * **Dynamic Host Configuration Protocol (DHCP)** automates the assignment of IP addresses, subnet masks, gateways, and other network parameters to devices on a network.

     **How It Works:**
   1. **Discovery**: A client broadcasts a DHCP request to locate servers.
   2. **Offer**: A DHCP server responds with an IP address and configuration offer.
   3. **Request**: The client requests the offered configuration.
   4. **Acknowledgment**: The server acknowledges and finalizes the configuration.

This simplifies network management by avoiding manual IP address assignments.


3. **Cloud Computing**: Describe AWS Lambda.
   * AWS Lambda is a **serverless compute service** that automatically runs your code in response to events. It scales automatically and only charges for the compute time used.

    **Key Features:**
   - **Trigger-Based Execution**: Events from AWS services like S3, DynamoDB, or API Gateway.
   - **No Server Management**: AWS handles the infrastructure.
   - **Pay-as-You-Go**: Billed based on execution time and requests.

    **Use Cases:**
   - Real-time data processing.
   - Backend for APIs.
   - Automation tasks.


4. **DevOps**: Define blue-green deployment.
   * **Blue-green deployment** is a release strategy that minimizes downtime and risks by running two environments:
    - **Blue**: The current live environment.
    - **Green**: The new environment with updated features.

    **Process:**
   1. Deploy the new version to the green environment.
   2. Redirect traffic from blue to green once verified.
   3. Retain blue as a backup for rollback.


5. **Tools & Technology**: Install Terraform and create a simple EC2 instance.
   * **Steps:**
   1. **Install Terraform**:
    - Download the binary for your OS from [Terraform's website](https://www.terraform.io/downloads).
    - Extract and move it to your PATH (e.g., `/usr/local/bin/`).

      Verify installation:
   ```bash
   terraform version
   ```

   2. **Write Terraform Configuration** (`main.tf`):
    ```hcl
    provider "aws" {
     region = "us-east-1"
   }

   resource "aws_instance" "example" {
     ami           = "ami-0c55b159cbfafe1f0" # Replace with a valid AMI
     instance_type = "t2.micro"
   }
   ```

   3. **Initialize, Plan, and Apply**:
   ```bash
   terraform init
   terraform plan
   terraform apply
   ```


6. **Scenario**: You need to deploy to multiple environments. How would you set this up?
   * **Approach**:
    - Use **Infrastructure as Code (IaC)** tools like Terraform or AWS CloudFormation.
    - Define variables for environments like `dev`, `staging`, and `prod`.
    - Store environment-specific configurations in separate files.

     **Example Terraform Setup:**
   1. **Directory Structure**:
     ```
     ├── environments/
     │   ├── dev.tfvars
     │   ├── staging.tfvars
     │   └── prod.tfvars
     ├── main.tf
     ├── variables.tf
     ```

   2. **Run Commands**:
     ```bash
     terraform apply -var-file="environments/dev.tfvars"
     terraform apply -var-file="environments/staging.tfvars"
     terraform apply -var-file="environments/prod.tfvars"
     ```

By automating deployments, consistency and efficiency improve across environments.

