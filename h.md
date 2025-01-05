# Day 56

1. **Linux**: Use `grep` with regex for advanced text searching.
   * The `grep` command is a powerful tool for searching text using patterns. With regular expressions (regex), you can perform advanced search operations. Examples:  
    - **Search for lines starting with "error":**  
      ```bash
      grep '^error' log.txt
      ```
    - **Find lines ending with ".com":**  
      ```bash
      grep '\.com$' file.txt
      ```
    - **Match lines containing a phone number pattern (123-456-7890):**  
      ```bash
      grep -E '[0-9]{3}-[0-9]{3}-[0-9]{4}' file.txt
      ```
    - **Search recursively in a directory:**  
      ```bash
      grep -r 'pattern' /path/to/directory
      ```


2. **Networking**: Explain the OSI model, especially Layers 4 and 7.

3. **Cloud Computing**: Define AWS Lambda and its use cases.

4. **DevOps**: Discuss the pros and cons of serverless computing.

5. **Tools & Technology**: Deploy a simple AWS Lambda function.

6. **Scenario**: You need a low-cost, scalable solution for a simple API. Would Lambda be suitable?

