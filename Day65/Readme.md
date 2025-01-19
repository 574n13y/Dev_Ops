# Day 65

1. **Linux**: Explore disk space and inode usage using `df` and `du`.
  - **`df`** (Disk Free):
   - Displays disk space usage for file systems.
   - Example command:
    ```bash
    df -h
    ```
    - `-h`: Human-readable format (e.g., MB, GB).

  - **`du`** (Disk Usage):
   - Shows directory/file space usage.
   - Example command:
    ```bash
    du -sh /path/to/directory
    ```
    - `-s`: Summarize total size.
    - `-h`: Human-readable format.

  - **Inode Usage**:
   - Use `df` to view inode usage:
    ```bash
    df -i
    ```
    - Displays available and used inodes (useful for systems with many small files).


2. **Networking**: What is a firewall, and how does it help in network security?
   - **Firewall Definition**:
  A firewall is a network security device or software that monitors and controls incoming and outgoing traffic based on predefined security rules.

   - **How It Helps in Security**:
    1. **Traffic Filtering**: Blocks unauthorized access while allowing legitimate traffic.
    2. **Prevents Attacks**: Protects against malicious traffic, such as DDoS, port scanning, and exploits.
    3. **Access Control**: Defines rules to permit or deny specific IPs, protocols, or ports.
    4. **Segmentation**: Enforces isolation between network zones.


3. **Cloud Computing**: Describe VPC subnetting and how it improves network segmentation.
   - **VPC Subnetting**:
    - Subnetting divides a VPC CIDR block into smaller subnets.
    - Subnets can be public (accessible from the internet) or private (restricted to internal resources).
  
   - **Improving Network Segmentation**:
    1. **Isolation**: Public-facing and internal resources are separated.
    2. **Security**: Fine-grained control over access using security groups and Network ACLs.
    3. **Efficient Routing**: Configures route tables for optimized traffic flow.


4. **DevOps**: Define configuration drift and how to detect it.
  - **Configuration Drift**:
   - Occurs when the actual state of infrastructure or systems diverges from the defined configuration in code or documentation.
   - Common causes:
    - Manual changes to infrastructure.
    - Unmanaged updates or patches.

  - **How to Detect It**:
    1. **Configuration Management Tools**: Tools like Ansible, Puppet, or Chef can flag deviations.
    2. **Infrastructure as Code (IaC)**: Tools like Terraform or AWS CloudFormation detect changes during plan or deployment stages.
    3. **Periodic Audits**: Regularly check the infrastructure against the desired state.


5. **Tools & Technology**: Use Terraform to create a VPC with subnets.

```hcl
provider "aws" {
  region = "us-east-1"
}

resource "aws_vpc" "main_vpc" {
  cidr_block = "10.0.0.0/16"
  tags = {
    Name = "MainVPC"
  }
}

resource "aws_subnet" "public_subnet" {
  vpc_id     = aws_vpc.main_vpc.id
  cidr_block = "10.0.1.0/24"
  map_public_ip_on_launch = true
  availability_zone       = "us-east-1a"
  tags = {
    Name = "PublicSubnet"
  }
}

resource "aws_subnet" "private_subnet" {
  vpc_id     = aws_vpc.main_vpc.id
  cidr_block = "10.0.2.0/24"
  availability_zone       = "us-east-1a"
  tags = {
    Name = "PrivateSubnet"
  }
}

resource "aws_internet_gateway" "main_igw" {
  vpc_id = aws_vpc.main_vpc.id
  tags = {
    Name = "MainIGW"
  }
}

resource "aws_route_table" "public_rt" {
  vpc_id = aws_vpc.main_vpc.id
  tags = {
    Name = "PublicRT"
  }
}

resource "aws_route" "public_route" {
  route_table_id         = aws_route_table.public_rt.id
  destination_cidr_block = "0.0.0.0/0"
  gateway_id             = aws_internet_gateway.main_igw.id
}

resource "aws_route_table_association" "public_subnet_association" {
  subnet_id      = aws_subnet.public_subnet.id
  route_table_id = aws_route_table.public_rt.id
}
```

   1. **Create a VPC**: CIDR block `10.0.0.0/16`.
   2. **Create Subnets**: 
   - Public Subnet: `10.0.1.0/24`, public IPs enabled.
   - Private Subnet: `10.0.2.0/24`.
   3. **Internet Gateway**: Attaches to the VPC for public internet access.
   4. **Route Table**: Defines a route for public traffic.


6. **Scenario**: You need a VPC with public and private subnets. How would you design this?
   * **Design**:
    1. **VPC**:
    - CIDR block: `10.0.0.0/16`.
    2. **Subnets**:
    - Public Subnet: `10.0.1.0/24` (for public-facing resources like ALB).
    - Private Subnet: `10.0.2.0/24` (for backend resources like EC2, RDS).
    3. **Route Tables**:
    - Public Subnet Route Table: Route to an Internet Gateway.
    - Private Subnet Route Table: Route traffic through a NAT Gateway (for outbound internet).
    4. **NAT Gateway**:
    - Enables private subnet instances to access the internet securely.
    5. **Security Groups**:
    - Public Subnet: Allow inbound traffic on specific ports (e.g., HTTP/HTTPS).
    - Private Subnet: Allow traffic only from specific sources (e.g., the public subnet).


