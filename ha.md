# Day 66

1. **Linux**: Manage file compression using gzip and tar.
  - **`gzip`**: Compresses files into `.gz` format.
   - Example: Compress a file
    ```bash
    gzip file.txt
    ```
    - Result: `file.txt.gz`
   - Decompress:
    ```bash
    gunzip file.txt.gz
    ```

  - **`tar`**: Archives multiple files into one and optionally compresses them.
   - Create a `.tar` archive:
    ```bash
    tar -cvf archive.tar file1 file2 directory/
    ```
    - `-c`: Create
    - `-v`: Verbose (show progress)
    - `-f`: Output file

   - Compress with `gzip`:
    ```bash
    tar -czvf archive.tar.gz file1 file2 directory/
    ```

   - Extract an archive:
    ```bash
    tar -xzvf archive.tar.gz
    ```


2. **Networking**: Explain the difference between Layer 4 and Layer 7 load balancing.
   - **Layer 4 Load Balancing**:
    - Operates at the **transport layer** (TCP/UDP).
    - Directs traffic based on IP address and port.
    - Fast and efficient, as it doesn’t inspect packet content.
    - Example: AWS **Network Load Balancer (NLB)**.

   - **Layer 7 Load Balancing**:
    - Operates at the **application layer** (HTTP/HTTPS).
    - Routes traffic based on content (e.g., URL, headers).
    - Supports advanced features like SSL termination and URL-based routing.
    - Example: AWS **Application Load Balancer (ALB)**.


3. **Cloud Computing**: What is AWS Transit Gateway, and how does it work?
   - **AWS Transit Gateway**:
    - A central hub that simplifies network management by connecting multiple VPCs, on-premises networks, and AWS services.

   - **How It Works**:
    1. **Attachment**: Connects resources (VPCs, VPNs, Direct Connect).
    2. **Routing**: Automatically propagates routes between attached resources.
    3. **Scalability**: Supports thousands of VPCs and routes in a single gateway.

   - **Use Cases**:
    - Simplifying multi-VPC connectivity.
    - Centralized control of network traffic.
    - Hybrid cloud setups (integrating on-premises and cloud networks).


4. **DevOps**: Discuss the principles of continuous testing.
   - **Continuous Testing**:
    - Integrates automated testing at every stage of the CI/CD pipeline to identify issues early.

   - **Principles**:
    1. **Automation**: Automate as many test cases as possible (unit, integration, performance).
    2. **Shift Left**: Test early in the development cycle to catch defects sooner.
    3. **Fast Feedback**: Ensure quick results for faster decision-making.
    4. **Test Coverage**: Cover different scenarios (functional, non-functional, edge cases).
    5. **Environment Parity**: Test in environments similar to production.


5. **Tools & Technology**: Configure an AWS Transit Gateway for VPC peering.
    1. **Create a Transit Gateway**:
      ```bash
      aws ec2 create-transit-gateway --description "MyTransitGateway"
      ```
    
    2. **Attach VPCs to the Transit Gateway**:
    - Attach VPC A:
      ```bash
       aws ec2 create-transit-gateway-vpc-attachment \
        --transit-gateway-id tgw-xxxxxxxx \
        --vpc-id vpc-aaaaaaa \
        --subnet-ids subnet-1111111 subnet-2222222
      ```
    - Attach VPC B:
      ```bash
       aws ec2 create-transit-gateway-vpc-attachment \
        --transit-gateway-id tgw-xxxxxxxx \
        --vpc-id vpc-bbbbbbb \
        --subnet-ids subnet-3333333 subnet-4444444
      ```
    
    3. **Update Route Tables**:
    - Add routes in each VPC’s route table pointing to the Transit Gateway.
    
    4. **Propagate Routes**:
    - Enable route propagation in the Transit Gateway route table.


6. **Scenario**: Your organization needs a central routing solution across multiple VPCs. How would you implement this?

