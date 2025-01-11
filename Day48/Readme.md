# Day 48

1. **Linux**: Practice file compression using `gzip` and `bzip2`.
   - **`gzip`**:
    - Compress a file:
      ```bash
      gzip filename
      ```
    - Decompress a file:
      ```bash
      gunzip filename.gz
      ```
    - View compression ratio:
      ```bash
      gzip -l filename.gz
      ```

   - **`bzip2`**:
    - Compress a file:
      ```bash
      bzip2 filename
      ```
    - Decompress a file:
      ```bash
      bunzip2 filename.bz2
      ```
    - Faster compression with `pbzip2` (parallel version of bzip2):
      ```bash
      pbzip2 filename
      ```

   **Key Differences**:
   - `gzip`: Faster, less compression.
   - `bzip2`: Slower, better compression.



2. **Networking**: Explain the purpose and basics of IPsec.
   - **What is IPsec?**  
  Internet Protocol Security (IPsec) is a suite of protocols designed to secure IP communications by authenticating and encrypting each packet in a data stream.

   - **Purpose**:
    - Provides **data integrity**, **authentication**, and **encryption**.
    - Protects data during transit over untrusted networks like the Internet.
    - Used in VPNs (Virtual Private Networks) to secure connections.

   - **Key Components**:
    1. **Authentication Header (AH)**: Ensures data integrity and authenticity.
    2. **Encapsulating Security Payload (ESP)**: Provides confidentiality, integrity, and authentication.
    3. **IKE (Internet Key Exchange)**: Establishes security associations and manages encryption keys.



3. **Cloud Computing**: Describe AWS Elastic File System (EFS) and its use cases.
   - **What is EFS?**  
  AWS Elastic File System (EFS) is a fully managed, scalable, shared file storage service for use with AWS services like EC2.

  - **Features**:
   - **Elastic**: Automatically scales up or down.
   - **Shared Access**: Multiple EC2 instances can mount the same file system.
   - **Durability**: Stores data redundantly across multiple Availability Zones (AZs).
   - **Performance Modes**:
    - General Purpose: Low latency.
    - Max I/O: High throughput for massive workloads.

   - **Use Cases**:
    - Shared storage for web servers.
    - Content management systems.
    - Machine learning and big data analytics.



4. **DevOps**: What is release management, and why is it important?
   - **Release Management**:  
  The process of planning, scheduling, and controlling the deployment of software releases to ensure they are delivered efficiently and with minimal risk.

   - **Key Activities**:
    - Coordinating between teams (Dev, QA, Ops).
    - Creating release plans and schedules.
    - Managing rollback plans in case of failure.

   - **Importance**:
    - Ensures **reliable deployments** with minimal downtime.
    - Provides **visibility** and control over changes.
    - Improves **customer satisfaction** by delivering high-quality features.



5. **Tools & Technology**: Use Terraform to deploy an EFS mount to an EC2 instance.
   * **Steps to Set Up Using Terraform**:

   1. **Define an EFS File System**:
      ```hcl
      resource "aws_efs_file_system" "example" {
        creation_token = "efs-example"
        lifecycle_policy {
            transition_to_ia = "AFTER_30_DAYS"
          }
       }
      ```

   2. **Create a Security Group**:
      ```hcl
      resource "aws_security_group" "efs_sg" {
         name_prefix = "efs-sg-"
           ingress {
             from_port   = 2049
             to_port     = 2049
             protocol    = "tcp"
             cidr_blocks = ["0.0.0.0/0"]
            }
         }
      ```

   3. **Attach EFS to EC2 Instance**:
    - Mount the EFS file system in your user data script:
       ```bash
       sudo yum install -y amazon-efs-utils
       sudo mount -t efs fs-12345678:/ /mnt/efs
       ```

   4. **Deploy with Terraform**:
      ```bash
      terraform init
      terraform apply
      ```

   - Click [Here](https://github.com/574n13y/dev/blob/main/deploy_Efs%26_attach_to_Ec2.tf) for  complete tf script 

6. **Scenario**: A high-availability application needs shared storage. What AWS solution would you recommend?
   - **Recommendation**: AWS Elastic File System (EFS).
   - **Why?**  
    - Fully managed and highly available across multiple AZs.
    - Scalable and supports simultaneous access from multiple EC2 instances.
    - Compatible with services like Kubernetes (EKS) and Lambda.

   - **Alternative Options**:
    - **Amazon FSx**: For Windows- or Lustre-based workloads.
    - **Amazon S3**: For object-based storage with higher durability.


