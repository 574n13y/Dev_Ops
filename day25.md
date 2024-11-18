# Day 25
---

1. **Linux**: Explain the difference between hard and soft links. Create an example.
   #### **Hard Links**
    - Directly reference the inode (physical location on disk) of a file.
    - Changes made to the original file are reflected in the hard link.
    - Even if the original file is deleted, the hard link retains the data.

   #### **Soft Links (Symbolic Links)**
    - A shortcut pointing to the original file’s path.
    - If the original file is deleted, the soft link becomes broken.
    - Can link across different file systems or partitions.

   #### **Example**
    ```bash
    # Create a file
    echo "Hello, World!" > original.txt

    # Create a hard link
    ln original.txt hardlink.txt

    # Create a soft link
    ln -s original.txt softlink.txt
    ```

   #### **Verify**
    ```bash
    ls -li
    ```
This will show identical inodes for `original.txt` and `hardlink.txt`, while `softlink.txt` has a different inode.


2. **Networking**: What are network layers, and how do they work?
   ### **What Are Network Layers, and How Do They Work?**

Network layers are conceptual divisions of a communication system that describe how data moves from one device to another over a network. The most widely known model for network layers is the **OSI (Open Systems Interconnection) Model**, which consists of seven layers, each with a specific role in data communication.

---

### **The OSI Model: 7 Layers**

1. **Physical Layer (Layer 1)**  
   - **Role**: Deals with the hardware aspects of network communication, such as cables, switches, and transmission of raw bits (0s and 1s).  
   - **Examples**: Ethernet cables, Wi-Fi signals.  
   - **Functionality**: Converts digital data into electrical, optical, or radio signals.

2. **Data Link Layer (Layer 2)**  
   - **Role**: Ensures reliable node-to-node data transfer and handles error detection and correction.  
   - **Examples**: MAC (Media Access Control) addresses, Ethernet.  
   - **Functionality**: Organizes data into frames for transmission and adds hardware addresses.

3. **Network Layer (Layer 3)**  
   - **Role**: Responsible for routing data packets between devices across different networks.  
   - **Examples**: IP (Internet Protocol), routers.  
   - **Functionality**: Adds logical addressing (IP addresses) and chooses the best path for data delivery.

4. **Transport Layer (Layer 4)**  
   - **Role**: Ensures end-to-end communication, reliability, and flow control.  
   - **Examples**: TCP (Transmission Control Protocol), UDP (User Datagram Protocol).  
   - **Functionality**: Breaks data into segments, ensures delivery, and manages retransmissions if needed.

5. **Session Layer (Layer 5)**  
   - **Role**: Establishes, manages, and terminates sessions between applications.  
   - **Examples**: APIs, session tokens.  
   - **Functionality**: Keeps track of data streams and ensures proper synchronization.

6. **Presentation Layer (Layer 6)**  
   - **Role**: Converts data into a format suitable for the application layer and handles encryption and compression.  
   - **Examples**: SSL/TLS encryption, JPEG, PNG.  
   - **Functionality**: Translates data between the application layer and the network.

7. **Application Layer (Layer 7)**  
   - **Role**: Provides a user interface and access to network services.  
   - **Examples**: HTTP, FTP, DNS.  
   - **Functionality**: Enables users and applications to interact with the network.

---

### **How They Work Together**
- **Data Encapsulation**: When sending data, each layer adds its own header (control information). For example:
  1. The application layer generates the message.
  2. The transport layer segments the data and adds a header.
  3. The network layer adds IP addresses.
  4. The data link layer organizes it into frames with MAC addresses.
  5. The physical layer transmits the data over the medium.

- **Data Decapsulation**: On the receiving end, the layers process the data in reverse, stripping headers at each layer and passing the payload to the next layer.

---

### **Real-World Example**
When you open a website (e.g., `www.example.com`):
1. **Application Layer**: Sends an HTTP request to load the page.
2. **Transport Layer**: Breaks the request into segments using TCP.
3. **Network Layer**: Routes the request using IP to the destination server.
4. **Data Link and Physical Layers**: Transmit the request over the internet to the server.
5. The server processes the request and sends back the response, which follows the same layered process in reverse.


3. **Cloud Computing**: Describe AWS IAM roles and policies.
   #### **IAM Roles**
- Used to delegate access permissions to AWS resources.
- Assigned to AWS services or users.
- Do not require access keys; instead, temporary credentials are issued.

#### **IAM Policies**
- JSON documents that define permissions.
- Can be attached to users, groups, or roles.
- Specify actions, resources, and conditions.

**Example Policy**: Grant `S3:Read` access to a specific bucket.
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::example-bucket/*"
    }
  ]
}
```

**Use Case**:
- Attach a role with this policy to an EC2 instance to allow it to access the S3 bucket.


4. **DevOps**: Explain the benefits of containerization.
   #### **Key Benefits**
    1. **Consistency**: Ensures the application behaves the same across environments.
    2. **Isolation**: Encapsulates applications and their dependencies.
    3. **Scalability**: Easily scale containers horizontally.
    4. **Portability**: Containers can run on any system with a container runtime.
    5. **Resource Efficiency**: Shares the host OS kernel, reducing overhead compared to VMs.
    6. **Simplified CI/CD**: Streamlines building, testing, and deploying applications.
**Popular Tool**: Docker is the most widely used containerization tool.


5. **Tools & Technology**: Use Docker to create a custom image.
   #### **Steps to Create a Custom Docker Image**
   1. **Create a Dockerfile**:
      ```Dockerfile
      # Use the official Python base image
      FROM python:3.9-slim

      # Set the working directory
      WORKDIR /app

      # Copy application files
      COPY . .

      # Install dependencies
      RUN pip install -r requirements.txt

      # Specify the command to run the app
      CMD ["python", "app.py"]
      ```

   2. **Build the Docker Image**:
      ```bash
      docker build -t my-python-app .
      ```

   3. **Run the Container**:
      ```bash
      docker run -d -p 5000:5000 my-python-app
      ```

   4. **Access the Application**:
   Open a browser and navigate to `http://localhost:5000`.


6. **Scenario**: An application needs to run on multiple servers. How would you design the deployment?
   #### **Solution: Use a Load Balancer with Orchestrated Containers**

   1. **Design**:
    - Deploy the application on multiple servers using container orchestration (e.g., Kubernetes or Docker Swarm).
    - Place a load balancer in front to distribute traffic.

   2. **Steps**:
   - **Containerize the Application**:
     Use Docker to package the app into an image.
   - **Set Up Orchestration**:
     Deploy using Kubernetes:
   - Create a `Deployment` to manage replicas.
    - Use a `Service` to expose the application.
   - **Configure Load Balancer**:
    - Use AWS Elastic Load Balancer (ELB) or Nginx as a reverse proxy.

   3. **Tools**:
   - **Docker Compose** for local multi-container setups.
   - **Terraform** for automated infrastructure provisioning.
   - **Kubernetes** for production-grade orchestration.


