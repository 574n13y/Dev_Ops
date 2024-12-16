# Day 40


1. **Linux**: Explore `awk` for text processing in files.
   * `awk` is a powerful text-processing tool in Linux that allows you to manipulate, filter, and analyze text files or streams. It works by splitting lines of text into fields and processing them using patterns and actions.

#### **Basic Examples:**
  1. **Print a Specific Column:**
     ```bash
     awk '{print $2}' file.txt  # Prints the second column of each line.
     ```

  2. **Filter Rows by a Condition:**
      ```bash
      awk '$3 > 100 {print $1, $3}' file.txt
      ```
    - Filters rows where the third column is greater than 100 and prints the first and third columns.

  3. **Search and Replace:**
     ```bash
     awk '{gsub("old", "new"); print}' file.txt
     ```
    - Replaces all occurrences of "old" with "new" in the file.



2. **Networking**: What is packet sniffing, and how is it used in troubleshooting?
   * #### **What is Packet Sniffing?**
Packet sniffing is the process of capturing and analyzing network traffic data. It involves intercepting data packets that travel across a network for monitoring and troubleshooting purposes.

  #### **Uses in Troubleshooting:**
   - **Diagnosing Network Latency:** Analyze packets to identify bottlenecks or delays.
   - **Inspecting Security Issues:** Detect unauthorized traffic or potential attacks.
   - **Debugging Communication Issues:** Verify proper communication between systems.
   - **Protocol Analysis:** Examine packets for compliance with expected protocols.

#### **Common Tools for Packet Sniffing:**
   - **Wireshark:** A popular GUI-based packet analysis tool.
   - **tcpdump:** A CLI-based tool for capturing network packets in real-time.

   Example (using `tcpdump`):
   ```bash
   tcpdump -i eth0 port 80  # Capture HTTP traffic on eth0 interface.
   ```


3. **Cloud Computing**: Explain the role of security groups in AWS.

4. **DevOps**: What is Infrastructure as Code (IaC)?

5. **Tools & Technology**: Write a Terraform configuration to create an EC2 instance.

6. **Scenario**: Your team requires automated deployment of infrastructure. How would you set this up?


