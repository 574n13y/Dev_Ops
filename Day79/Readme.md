# Day 79



1. **Linux**: Explore process management with `nice` and `renice`.
   - In Linux, **`nice`** and **`renice`** manage process priority to control CPU usage:  
    
    1. **`nice` – Set Process Priority on Start**
    - The **nice value** ranges from **-20 (highest priority)** to **19 (lowest priority)**.
    - Example: Start a process with a lower priority:  
      ```bash
      nice -n 10 python3 script.py
      ```
    
    2. **`renice` – Change Priority of a Running Process**
    - Use **`renice`** to adjust the priority of an existing process:  
      ```bash
      renice -5 -p 1234  # Increase priority for process with PID 1234
      ```

  🔹 **Use Case:** Optimize system performance by lowering non-critical background tasks (e.g., backups, indexing) and giving priority to critical workloads.  


2. **Networking**: Explain DNS forwarding and its use cases.
   - DNS forwarding **redirects queries** from one DNS server to another, usually when the server **cannot resolve** the request itself.  

   * **Types of DNS Forwarding**  
    1. **Conditional Forwarding** – Forward requests to a specific server based on domain name.  
    2. **Recursive Forwarding** – Forward all unknown queries to an external resolver (e.g., Google's `8.8.8.8`).  

   * **Use Cases**  
    - **Corporate Networks**: Internal DNS servers forward unresolved requests to a public DNS.  
    - **Hybrid Cloud**: On-prem servers forward cloud-based domain queries to AWS Route 53.  
    - **Content Filtering**: Organizations use DNS forwarding to enforce access policies via third-party resolvers.  

  🔹 **Example in AWS:** Route 53 **Resolver Forwarding** is used for hybrid architectures.  


3. **Cloud Computing**: Describe the components of AWS CloudFormation and create a simple CloudFormation template.
   * **Key Components of AWS CloudFormation**  
    1. **Templates** – YAML/JSON files that define infrastructure.  
    2. **Stacks** – A collection of AWS resources managed as a unit.  
    3. **Change Sets** – Preview changes before applying them.  
    4. **Drift Detection** – Identify manual modifications outside CloudFormation.  

   * **Example: Deploy an EC2 Instance with CloudFormation**  
     
     ```yaml
     AWSTemplateFormatVersion: '2010-09-09'
     Resources:
       MyEC2Instance:
         Type: AWS::EC2::Instance
         Properties:
           InstanceType: t2.micro
           ImageId: ami-0abcdef1234567890
           KeyName: my-key-pair
           Tags:
             - Key: Name
             Value: MyInstance
     ```

   🔹 **Why Use CloudFormation?**  
    - Automates infrastructure as code (IaC).  
    - Ensures repeatable deployments.  
    - Provides rollback and change tracking.  


4. **DevOps**: Define Idempotency in configuration management and its importance.
   * Idempotency ensures that running an operation **multiple times** has the **same effect** as running it once.  

   * **Why is Idempotency Important?**  
    - **Prevents duplicate changes** – No accidental resource creation.  
    - **Ensures consistency** – Running a script multiple times results in the same configuration.  
    - **Reliable automation** – Terraform, Ansible, and Puppet follow this principle.  

   * **Example with Ansible (Idempotent Playbook)**  
     ```yaml
     - name: Ensure Apache is installed
       apt:
         name: apache2
         state: present
     ```
  🔹 Running this playbook **multiple times won’t reinstall** Apache unnecessarily.  


5. **Tools & Technology**: Deploy an EC2 instance using CloudFormation.
   * **Steps to Deploy Using AWS CLI**  
    1. **Create a YAML Template** (similar to the example in Section 3).  
    
    2. **Upload and Deploy Using AWS CLI**  
       ```bash
       aws cloudformation create-stack --stack-name MyEC2Stack --template-body file://ec2-template.yaml
       ```
    
    3. **Check Stack Status**  
       ```bash
       aws cloudformation describe-stacks --stack-name MyEC2Stack
       ```

   🔹 **Why CloudFormation?**  
    - Automates and standardizes deployments.  
    - Easy to rollback failed changes.  
    - Helps in scaling infrastructure efficiently.  


6. **Scenario**: You need to automate infrastructure creation for different environments. How would you design it?
   - Example: Use **Parameters** for different instance types in environments.  

```yaml
AWSTemplateFormatVersion: '2010-09-09'
Parameters:
  Environment:
    Type: String
    Default: dev
    AllowedValues:
      - dev
      - staging
      - prod
  InstanceType:
    Type: String
    Default: t2.micro
    AllowedValues:
      - t2.micro
      - t2.medium
      - t2.large
Resources:
  MyEC2Instance:
    Type: AWS::EC2::Instance
    Properties:
      InstanceType: !Ref InstanceType
      ImageId: ami-0abcdef1234567890
```

- Deploy Using AWS CLI with Environment-Specific Parameters**  
```bash
aws cloudformation create-stack --stack-name DevStack \
  --template-body file://ec2-template.yaml \
  --parameters ParameterKey=Environment,ParameterValue=dev
```


