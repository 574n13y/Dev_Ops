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
   - **S3 Storage Classes**:
   1. **S3 Standard**:  
    - High availability, durability, and performance.  
    - Best for frequently accessed data.
    - Cost: $$$

   2. **S3 Intelligent-Tiering**:  
    - Automatically moves data between access tiers based on usage.
    - Best for data with unpredictable access patterns.
    - Cost: $$ (monitoring fee applies).

   3. **S3 Standard-IA (Infrequent Access)**:  
    - Lower storage costs, higher retrieval costs.
    - Best for infrequently accessed data.
    - Cost: $

   4. **S3 One Zone-IA**:  
    - Same as Standard-IA but stored in a single AZ.
    - Best for data that can be recreated if lost.
    - Cost: $

   5. **S3 Glacier**:  
    - Low-cost storage for long-term archiving.
    - Retrieval times: Minutes to hours.
    - Cost: $$ (retrieval fees).

   6. **S3 Glacier Deep Archive**:  
    - Cheapest option for data accessed once or twice a year.
    - Retrieval times: 12+ hours.
    - Cost: $


4. **DevOps**: Define load testing, stress testing, and performance testing.
   - **Load Testing**:
    - Tests system behavior under expected load conditions.
    - Goal: Ensure the system meets performance expectations.

   - **Stress Testing**:
    - Tests system behavior under extreme conditions (beyond maximum capacity).
    - Goal: Identify system breaking points.

   - **Performance Testing**:
    - Broad category encompassing load and stress tests.
    - Goal: Evaluate system speed, scalability, and responsiveness.


5. **Tools & Technology**: Set up a basic load test with Apache JMeter.
   * **Steps to Set Up Apache JMeter**:
   1. **Download and Install JMeter**:
    - Download: [JMeter Official Site](https://jmeter.apache.org/download_jmeter.cgi).
    - Extract and run:  
       ```bash
       ./jmeter
       ```

   2. **Create a Test Plan**:
    - Add a **Thread Group** (number of users, ramp-up time, loops).
    - Add a **Sampler** (HTTP Request) to simulate API calls.
    - Add a **Listener** (View Results Tree) to view the test outcome.

   3. **Run the Test**:
    - Start the test by clicking the green triangle button.
    - Analyze the results in the Listener.


6. **Scenario**: An application needs to handle sudden traffic spikes. How would you test it?


