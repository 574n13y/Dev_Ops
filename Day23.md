# Day 23

---

1. **Linux**: Use the `cp` command to copy files and directories.
   - The `cp` command is used to copy files and directories in Linux. 

   - **Basic syntax**:  
     ```
     cp [options] source destination
     ```
   - **Examples**:
    - Copy a file:  
     ```
     cp file.txt /path/to/destination/
     ```
    - Copy a directory (recursively):  
     ```
     cp -r /source/directory /path/to/destination/
     ```
    - Preserve file attributes:  
     ```
     cp -p file.txt /path/to/destination/
     ```


2. **Networking**: What is a MAC address, and how is it different from an IP address?
   - **MAC Address**:
    - Stands for **Media Access Control** address.
    - It is a unique hardware identifier assigned to a network interface card (NIC).
    - Format: **6 pairs of hexadecimal digits** (e.g., `00:1A:2B:3C:4D:5E`).
    - Works at the **Data Link Layer** (Layer 2) of the OSI model.
    - Typically remains constant and is device-specific.

   - **IP Address**:
    - Stands for **Internet Protocol** address.
    - It is a logical address assigned to a device on a network.
   - Format: 
    - IPv4: Four decimal numbers separated by dots (e.g., `192.168.1.1`).
    - IPv6: Eight groups of hexadecimal digits (e.g., `2001:0db8::1`).
    - Operates at the **Network Layer** (Layer 3).
    - Can change (e.g., dynamic IPs via DHCP).


3. **Cloud Computing**: List the benefits of using the cloud vs. on-premises infrastructure.
   - **Cost Efficiency**:
    - Cloud: Pay-as-you-go pricing, no upfront hardware costs.
    - On-Premises: Significant upfront investment for hardware and maintenance.

   - **Scalability**:
    - Cloud: Easily scale resources up or down.
    - On-Premises: Limited by physical hardware; scaling can be slow and expensive.

   - **Maintenance**:
    - Cloud: Handled by the cloud provider.
    - On-Premises: Requires dedicated IT staff for maintenance.

   - **Accessibility**:
    - Cloud: Accessible from anywhere with an internet connection.
    - On-Premises: Requires VPN or physical presence.

   - **Innovation and Speed**:
    - Cloud: Access to cutting-edge technology and rapid deployments.
    - On-Premises: Slower adoption of new technologies.


4. **DevOps**: What is continuous integration?
   - Continuous Integration (CI) is a DevOps practice where developers frequently merge their code changes into a shared repository. Automated tests and builds are triggered to ensure code quality and functionality.

   - **Benefits**:
    - Detects bugs early.
    - Reduces integration issues.
    - Speeds up development and deployment cycles.
   - **Popular Tools**: Jenkins, GitHub Actions, GitLab CI, CircleCI.


5. **Tools & Technology**: Install Node.js and run a basic script.
   - **Install Node.js**:
    1. On Linux:  
     ```
     sudo apt update
     sudo apt install nodejs npm
     ```
    2. Verify installation:  
     ```
     node -v
     npm -v
     ```

   - **Run a basic script**:
    1. Create a file named `app.js`:  
     ```javascript
     console.log("Hello, Node.js!");
     ```
    2. Run the script:  
     ```
     node app.js
     ```


6. **Scenario**: Your team wants to automate testing in a CI/CD pipeline. How would you set it up?

