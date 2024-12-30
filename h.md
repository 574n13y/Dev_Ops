# Day 52

1. **Linux**: Use `chown` to change file and directory ownership.
   - The `chown` command changes the **ownership** of files or directories in Linux.
   - Ownership has two parts:
    - **User**: The owner of the file.
    - **Group**: A group of users that can access the file.

   #### Syntax:
        ```bash
        chown [OPTIONS] USER[:GROUP] FILE
        ```

   #### Examples:
   - Change the owner of a file:
     ```bash
     chown john file.txt
     ```
   - Change the owner and group:
     ```bash
     chown john:developers file.txt
     ```
   - Change ownership recursively (e.g., for directories):
     ```bash
     chown -R john:developers /path/to/directory
     ```


2. **Networking**: Define MTU (Maximum Transmission Unit) and its effect on networks.
   - **MTU** is the largest size of a packet that can be transmitted over a network without fragmentation.
   
   - Default MTU sizes:
    - Ethernet: 1500 bytes.
    - Jumbo frames: Up to 9000 bytes.
   
   - **Impact of MTU**:
    - Larger MTU improves efficiency by reducing the number of packets.
    - Smaller MTU can reduce latency but increases overhead.
    - Mismatched MTU settings may cause packet loss or fragmentation.

   #### Use Case:
    - MTU tuning is essential for applications that transfer large files or stream video to avoid performance degradation.


3. **Cloud Computing**: Discuss AWS CloudWatch and its monitoring capabilities.

4. **DevOps**: Explain blue-green deployment and its advantages.

5. **Tools & Technology**: Set up a monitoring dashboard in CloudWatch for CPU and memory.

6. **Scenario**: Your application needs performance monitoring. How would you set it up?


