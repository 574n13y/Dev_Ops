# Day 43


1. **Linux**: Describe `chmod` in more detail and practice setting file permissions.
   * `chmod` is a Linux command used to change file or directory permissions. Permissions in Linux are defined by **read (r)**, **write (w)**, and **execute (x)** attributes for three categories:  

   1. **Owner**: The user who owns the file.  
   2. **Group**: A group of users who can access the file.  
   3. **Others**: All other users on the system.

   **Permission Syntax**:  
   - **Symbolic**: `chmod u+rwx file` (change permissions for user/owner).  
   - **Numeric**: Permissions are represented as a 3-digit number (e.g., `chmod 755 file`), where each digit defines the permission levels:  
    - **4**: Read  
    - **2**: Write  
    - **1**: Execute  
    - Sum of values determines permissions.  

    | Permission | Numeric | Description         |
    |------------|---------|---------------------|
    | `r--`      | 4       | Read-only          |
    | `rw-`      | 6       | Read and write     |
    | `rwx`      | 7       | Read, write, execute |

   **Example**:
     ```bash
     chmod 644 file  # Owner: rw-, Group: r--, Others: r--
     chmod u+x file  # Add execute permission for the owner
     chmod go-r file # Remove read permission for group and others
     ```


2. **Networking**: Explain the concept of subnets and subnetting.
   * A **subnet** is a logically divided segment of an IP network. Subnetting is the process of dividing a network into smaller, manageable pieces.  

   #### **Why Subnetting?**
   - Improves network performance by reducing broadcast domains.
   - Enhances security by isolating network segments.
   - Efficiently utilizes IP address space.

   **Subnet Mask**: Determines the range of IP addresses in a subnet.  
   - Example: `192.168.1.0/24` (subnet mask: `255.255.255.0`) allows for 256 IPs (254 usable).  

   **CIDR Notation**: Specifies the number of significant bits in the subnet mask.  
   - `/24`: 24 bits for the network, 8 bits for hosts.  

   #### **Subnetting Calculation**:
   1. Determine how many subnets or hosts you need.
   2. Use subnet mask bits to divide the network.
   3. Calculate the network range for each subnet.

    **Example**:
   - Original Network: `192.168.1.0/24`.
   - Subnets: `192.168.1.0/25` (128 IPs), `192.168.1.128/25` (128 IPs).


3. **Cloud Computing**: Describe AWS Route 53 and its use cases.

4. **DevOps**: Explain deployment strategies: rolling, blue-green, and canary.

5. **Tools & Technology**: Use Jenkins to set up a basic deployment pipeline.

6. **Scenario**: Your team wants to reduce deployment downtime. Which strategy would you recommend?


