# Day 20

---

1. **Linux**: Explain the `pwd` command to show the current directory. Describe absolute vs. relative paths.
  * **Linux**: `pwd` Command and Absolute vs. Relative Paths
   - **`pwd` Command**: The `pwd` (Print Working Directory) command is used in Linux to display the current directory in which the user is operating. When you type `pwd` and press Enter, it outputs the full path of the current directory.
     ```bash
     pwd
     ```
     Example output:
     ```
     /home/user/Documents
     ```

   - **Absolute vs. Relative Paths**:
     - **Absolute Path**: This path starts from the root directory (`/`) and specifies the full directory path. E.g., `/home/user/Documents/file.txt`.
     - **Relative Path**: This path is relative to the current directory and does not start with `/`. For instance, if you’re in `/home/user`, a relative path to the file could be `Documents/file.txt`.


2. **Networking**: Use `ping` to test network connectivity to google.com. What does `ping` verify?
   - **`ping` Command**: The `ping` command checks the network connectivity between your machine and a specified host by sending ICMP (Internet Control Message Protocol) echo requests. If the connection is successful, it receives echo replies. Use `ping` to test if you can reach an external server, like Google:
     ```bash
     ping google.com
     ```
     Output will show response times and other data, like the time it takes for packets to travel between your computer and the server.

   - **What Does `ping` Verify?**:
     - **Network connectivity** to the target host.
     - **Round-trip time** for packets to reach the host and return.
     - **Packet loss**, indicating any connection issues.
   

3. **Cloud Computing**: Define cloud computing and list the three main types of cloud services.
   - **Definition**: Cloud computing is the on-demand delivery of IT resources over the internet. Rather than owning physical data centers or servers, organizations can access technology services on an as-needed basis from a cloud provider.

   - **Three Main Types of Cloud Services**:
     1. **IaaS (Infrastructure as a Service)**: Provides virtualized computing resources over the internet, like servers and storage.
     2. **PaaS (Platform as a Service)**: Provides a platform allowing developers to build, deploy, and manage applications without dealing with infrastructure.
     3. **SaaS (Software as a Service)**: Delivers software applications over the internet, accessible via a web browser.


4. **DevOps**: Describe DevOps in your own words.
   - **DevOps** is a set of practices that combines development (Dev) and operations (Ops) to accelerate the software development lifecycle. By fostering collaboration, automation, and continuous improvement, DevOps helps teams to deliver better software faster, ensuring that changes are reliable and easily integrated into production environments.


5. **Tools & Technology**: Install Git. Create a new repository and commit a README file.
   - **Install Git**:
    - On Ubuntu/Debian:
       ```bash
       sudo apt update
       sudo apt install git
       ```
    - On macOS (Homebrew):
       ```bash
       brew install git
       ```
   - **Create a New Repository and Commit a README File**:
    1. **Initialize a Git Repository**:
        ```bash
        mkdir my-project
        cd my-project
        git init
        ```
    2. **Create a README File**:
        ```bash
        echo "# My Project" > README.md
        ```
    3. **Add and Commit**:
        ```bash
        git add README.md
        git commit -m "Add README file"
        ```

6. **Scenario**: You need to check if a server is running. What Linux and networking commands would you use?
   - **Check if the Server is Running**:
    - **`ping`**: Use `ping` to see if the server is reachable (if ICMP responses are allowed).
       ```bash
       ping <server-address>
       ```
    - **`curl` or `wget`**: For web servers, check HTTP response codes:
       ```bash
       curl -I http://<server-address>
       ```
    - A `200 OK` response indicates that the server is responding to HTTP requests.
    - **`netstat` or `ss`**: Check open ports and if the server is listening on a specific port (e.g., 80 or 443 for web services):
       ```bash
       netstat -tuln | grep <port>
       ```
    - **`telnet`**: Use `telnet` to see if a port is open, which is useful if the server has specific services running on specific ports.
       ```bash
       telnet <server-address> <port>
       ```
    - **`systemctl`** (if on the server itself): Check if a specific service is active.
       ```bash
       sudo systemctl status <service-name>
       ```
