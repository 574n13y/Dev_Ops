# Day 59

1. **Linux**: Use `df` and `du` for detailed disk usage insights.
   - **`df` (Disk Free)**: Provides an overview of disk space usage for file systems.
    - Example usage:
    ```bash
    df -h
    ```
    - `-h`: Displays output in human-readable format (e.g., MB, GB).
    - Output includes file system, used and available space, and mount points.

   - **`du` (Disk Usage)**: Shows detailed space usage for directories and files.
    - Example usage:
    ```bash
    du -h /path/to/directory
    ```
    - `-h`: Human-readable format.
    - Can use `du -sh` for a summary of total space used by a directory.

   Combine both tools for a comprehensive view of disk usage:
    ```bash
    df -h
    du -sh /var/log
    ```


2. **Networking**: Describe TCP three-way handshake.
   - The TCP three-way handshake establishes a reliable connection between a client and server:

   1. **SYN** (Synchronize): The client sends a SYN packet to initiate the connection, indicating it wants to establish communication.

   2. **SYN-ACK**: The server responds with a SYN-ACK packet to acknowledge the client’s request and indicates it is ready to establish a connection.

   3. **ACK** (Acknowledge): The client sends an ACK packet to acknowledge the server’s response, completing the handshake.

Once the handshake is complete, data transmission begins. This process ensures reliability and agreement on connection parameters.


3. **Cloud Computing**: Explain the difference between EC2 and Lambda.

4. **DevOps**: What are build artifacts, and how do you manage them?

5. **Tools & Technology**: Configure an S3 bucket as an artifact repository.

6. **Scenario**: Your team wants to store build artifacts. How would you set this up?


