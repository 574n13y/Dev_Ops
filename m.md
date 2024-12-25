# Day 47

1. **Linux**: Explore file permissions more with `umask`.
   - **`umask` Overview**:  
     `umask` is a command used to set the default permissions for new files and directories. It determines which permission bits will not be set when a file or directory is created.
   - Default permissions:
    - Files: 666 (read and write for all users)
    - Directories: 777 (read, write, and execute for all users)
   - The `umask` value subtracts permissions from these defaults.
  
   - **Examples**:
      ```bash
      umask 022  # New files: 644, New directories: 755
      umask 077  # New files: 600, New directories: 700
      umask      # View current umask value
      ```


2. **Networking**: What is ICMP, and how does it work?
  - **ICMP (Internet Control Message Protocol)**:
   - A network-layer protocol used by devices to communicate error messages and operational information.
   - Common uses:
    - **Ping**: Checks if a host is reachable.
    - **Traceroute**: Diagnoses the path packets take.
    - **Error Reporting**: Reports unreachable hosts or network issues.

  - **How it works**:
   - ICMP packets are encapsulated within IP packets but do not carry application data.
   - Types of ICMP messages:
    - Type 0: Echo Reply (response to ping)
    - Type 3: Destination Unreachable
    - Type 8: Echo Request (ping)


3. **Cloud Computing**: Explain the differences between AWS S3 storage classes.

4. **DevOps**: Define load testing, stress testing, and performance testing.

5. **Tools & Technology**: Set up a basic load test with Apache JMeter.

6. **Scenario**: An application needs to handle sudden traffic spikes. How would you test it?


