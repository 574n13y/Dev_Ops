# Day 36



1. **Linux**: Use `diff` to compare two files.
   * The `diff` command in Linux compares two files line by line and outputs the differences.  
    
     **Example Usage:**  
      ```bash
      diff file1.txt file2.txt
      ```
   - Output uses:  
    - `<` for lines in `file1` but not in `file2`.  
    - `>` for lines in `file2` but not in `file1`.  
     **Useful Options:**  
    - `diff -y file1.txt file2.txt`: Displays side-by-side comparison.  
    - `diff -c file1.txt file2.txt`: Context format to show surrounding lines for better understanding.


2. **Networking**: Explain SSL/TLS and how it secures data.
   * **SSL (Secure Sockets Layer)** and **TLS (Transport Layer Security)** are cryptographic protocols used to secure communication over a network.  
   
      **Key Features of SSL/TLS:**  
    - **Encryption:** Protects data in transit from eavesdropping.  
    - **Authentication:** Uses certificates to verify the identity of communicating parties.  
    - **Integrity:** Ensures transmitted data is not altered using message digests and hashing algorithms.  

    **How It Works:**  
   1. **Handshake Phase:**  
    - Client and server negotiate supported SSL/TLS versions and ciphers.  
    - Server presents its certificate, verified by the client.  
    - A shared session key is established for encryption.  
   2. **Data Transmission:**  
    - All communication is encrypted using the session key.  


3. **Cloud Computing**: What is an AWS VPC? Describe its basic components.

4. **DevOps**: Describe the importance of backup and restore strategies.

5. **Tools & Technology**: Create a backup script using `rsync`.

6. **Scenario**: A system needs regular data backups. How would you automate them?

