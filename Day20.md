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
 * **Networking**: Using `ping` to Test Network Connectivity
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
4. **DevOps**: Describe DevOps in your own words.
5. **Tools & Technology**: Install Git. Create a new repository and commit a README file.
6. **Scenario**: You need to check if a server is running. What Linux and networking commands would you use?
