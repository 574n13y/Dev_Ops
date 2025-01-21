# Day 67

1. **Linux**: Use `find` with advanced filters to search for files by size and date.
   * The `find` command can be used with options like `-size` and `-mtime` to search for files.  
   **Examples**:  
    - Find files larger than 100MB:  
      ```bash
      find /path/to/search -type f -size +100M
      ```
    - Find files modified in the last 7 days:  
      ```bash
      find /path/to/search -type f -mtime -7
      ```
    - Combine both:  
      ```bash
      find /path/to/search -type f -size +100M -mtime -7
      ```  


2. **Networking**: Explain how SSL/TLS encryption works and its importance.

3. **Cloud Computing**: Define data lifecycle management in AWS.

4. **DevOps**: What is the role of automated deployment approval in CI/CD pipelines?

5. **Tools & Technology**: Set up lifecycle policies for an S3 bucket.

6. **Scenario**: Your organization wants to automatically archive and delete older data. How would you configure this?

