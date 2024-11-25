# Day 28


1. **Linux**: Explain and test `grep` with a sample file.
    * The `grep` command is used to search for specific patterns within files. It’s a powerful tool for filtering lines based on regular expressions.

   #### **Example Usage**
        **Sample File (`data.txt`):**
      ```
      apple
      banana
      grape
      orange
      pineapple
      ```

      **Commands:**
   1. Find lines containing "apple":
      ```bash
      grep "apple" data.txt
      ```
      **Output:**
      ```
      apple
      pineapple
      ```
   
    2. Ignore case sensitivity:
      ```bash
      grep -i "APPLE" data.txt
      ```

   3. Display line numbers:
      ```bash
      grep -n "apple" data.txt
      ```
      **Output:**
      ```
      1:apple
      5:pineapple
      ```

   4. Use regular expressions:
      ```bash
      grep "^a" data.txt
      ```
      **Output:**
      ```
      apple
      ```


2. **Networking**: Describe TCP and UDP. What are the differences?
   #### **TCP (Transmission Control Protocol)**
    - **Reliable**: Ensures data delivery via acknowledgment and retransmissions.
    - **Connection-Oriented**: Establishes a connection before data transfer.
    - **Use Cases**: Web browsing (HTTP/HTTPS), email (SMTP), file transfer (FTP).

   #### **UDP (User Datagram Protocol)**
    - **Unreliable**: No acknowledgment; data may be lost.
    - **Connectionless**: Sends data without setting up a session.
    - **Use Cases**: Streaming, gaming, VoIP.

   #### **Key Differences**
   | Feature            | TCP                     | UDP               |
   |--------------------|-------------------------|-------------------|
   | **Reliability**    | Reliable (ACKs)         | Unreliable        |
   | **Speed**          | Slower (overhead)       | Faster            |
   | **Connection**     | Connection-Oriented     | Connectionless    |
   | **Data Loss**      | Prevents                | May occur         |
   | **Use Case**       | File transfer, emails   | Streaming, DNS    |


3. **Cloud Computing**: Describe the basic components of AWS S3.

4. **DevOps**: What’s source control? Explain its benefits.

5. **Tools & Technology**: Push a Git repository to GitHub.

6. **Scenario**: An application has multiple versions. How would you handle version control?
