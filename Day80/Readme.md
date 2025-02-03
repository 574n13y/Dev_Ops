# Day 80


1. **Linux**: Use `iptables` to set up basic firewall rules.
   - `iptables` is a tool to configure the Linux kernel firewall. Here’s how to set up some basic rules:

   - **Allow SSH (Port 22)**
     ```sh
     sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
     ```
   - **Allow HTTP & HTTPS (Ports 80, 443)**
     ```sh
     sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
     sudo iptables -A INPUT -p tcp --dport 443 -j ACCEPT
     ```
   - **Block all incoming traffic except allowed**
     ```sh
     sudo iptables -P INPUT DROP
     sudo iptables -P FORWARD DROP
     ```
   - **Save Rules (Ubuntu/Debian)**
     ```sh
     sudo iptables-save > /etc/iptables/rules.v4
     ```


2. **Networking**: Explain DHCP and its role in IP address assignment.
   - **Dynamic Host Configuration Protocol (DHCP)** is a network protocol that automatically assigns **IP addresses** to devices.
   - Without DHCP, devices would require manual IP configuration.
   - **How it works**:
    1. A new device sends a **DHCP Discovery** request.
    2. The **DHCP server** assigns an IP from its pool.
    3. The device receives **IP, subnet mask, gateway, and DNS settings**.


3. **Cloud Computing**: Describe AWS IAM roles and how they differ from IAM users.
   
   | Feature         | IAM Role | IAM User |
   |---------------|---------|---------|
   | Identity Type | Temporary security identity | Permanent user identity |
   | Credentials | Uses temporary STS tokens | Uses long-term credentials (username/password, access keys) |
   | Use Case | Assigned to AWS services (e.g., EC2, Lambda) | Assigned to people or applications |
   | Security | More secure, no static credentials | Can be less secure if credentials are leaked |

   **Example**: An **IAM role** can be assigned to an **EC2 instance** to grant access to an **S3 bucket** without needing hardcoded credentials.


4. **DevOps**: What is the principle of least privilege, and how does it apply to IAM?
   - **PoLP** means granting users and services only the permissions they absolutely need.
   - **Application in AWS IAM**:
    - Use **IAM policies** with **least privilege** rules.
    - **Deny by default** and only **allow specific actions**.
    - Use **IAM roles** instead of hardcoded credentials.


5. **Tools & Technology**: Create and assign an IAM role for an EC2 instance.
    1. **Create an IAM Role**:
    - Go to **IAM → Roles → Create Role**.
    - Select **EC2** as the trusted entity.
    - Attach a policy (e.g., `AmazonS3ReadOnlyAccess`).
    - Name the role (e.g., `EC2S3ReadOnlyRole`).
    
    2. **Attach the Role to an EC2 Instance**:
    - Go to **EC2 → Instances**.
    - Select the instance, then **Actions → Security → Modify IAM Role**.
    - Choose `EC2S3ReadOnlyRole` and save.
    
    3. **Verify Access** (Inside EC2):
       ```sh
       curl http://169.254.169.254/latest/meta-data/iam/security-credentials/
       ```


6. **Scenario**: You need secure, limited access to an S3 bucket for a specific application. How would you configure it?
    1. **Create an IAM Policy** (e.g., `S3LimitedAccessPolicy`):
       ```json
       {
         "Version": "2012-10-17",
         "Statement": [
           {
             "Effect": "Allow",
             "Action": ["s3:GetObject"],
             "Resource": ["arn:aws:s3:::my-secure-bucket/*"]
           }
         ]
       }
       ```
    
    2. **Attach the Policy to an IAM Role**.
    
    3. **Assign the Role to the Application’s EC2 Instance**.
    
    4. **Use AWS SDK or CLI** inside the application to access the S3 bucket.

---

```
provider "aws" {
  region = "us-east-1"
}

# IAM Policy for Read-Only Access to S3 Bucket
resource "aws_iam_policy" "s3_readonly_policy" {
  name        = "S3ReadOnlyPolicy"
  description = "Allows read-only access to a specific S3 bucket"
  policy      = jsonencode({
    Version = "2012-10-17"
    Statement = [
      {
        Effect   = "Allow"
        Action   = ["s3:GetObject"]
        Resource = "arn:aws:s3:::my-secure-bucket/*"
      }
    ]
  })
}

# IAM Role for EC2
resource "aws_iam_role" "ec2_s3_role" {
  name = "EC2S3ReadOnlyRole"
  assume_role_policy = jsonencode({
    Version = "2012-10-17"
    Statement = [
      {
        Effect = "Allow"
        Principal = {
          Service = "ec2.amazonaws.com"
        }
        Action = "sts:AssumeRole"
      }
    ]
  })
}

# Attach Policy to IAM Role
resource "aws_iam_role_policy_attachment" "s3_attach" {
  role       = aws_iam_role.ec2_s3_role.name
  policy_arn = aws_iam_policy.s3_readonly_policy.arn
}

# IAM Instance Profile
resource "aws_iam_instance_profile" "ec2_s3_profile" {
  name = "EC2S3ReadOnlyProfile"
  role = aws_iam_role.ec2_s3_role.name
}

# EC2 Instance (Attach IAM Role)
resource "aws_instance" "my_instance" {
  ami           = "ami-12345678"  # Replace with a valid AMI ID
  instance_type = "t2.micro"
  
  iam_instance_profile = aws_iam_instance_profile.ec2_s3_profile.name

  tags = {
    Name = "EC2-With-S3-Access"
  }
}

```

