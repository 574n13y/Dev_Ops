# Day 39

1. **Linux**: Use `sed` to edit text in files programmatically.
    -   `sed` (stream editor) is used to perform text transformations or edits on files programmatically.  

     **Examples:**  
   - Replace text:  
     ```bash
     sed 's/old_text/new_text/' file.txt
     ```  
      Replaces the first occurrence of `old_text` with `new_text` in each line.

   - Replace globally:  
     ```bash
     sed 's/old_text/new_text/g' file.txt
     ```  
      Replaces all occurrences of `old_text` with `new_text` in each line.

   - In-place edits:  
     ```bash
     sed -i 's/old_text/new_text/g' file.txt
     ```  
      Modifies the file directly without creating a new one.

   - Delete lines containing a pattern:  
     ```bash
     sed '/pattern/d' file.txt
     ```

2. **Networking**: What is DNS? Explain how it works.

3. **Cloud Computing**: Describe the concept of IAM (Identity and Access Management) in AWS.

4. **DevOps**: Define CI/CD pipelines and list their components.

5. **Tools & Technology**: Set up a basic pipeline in Jenkins to build and test code.

6. **Scenario**: A team needs automatic testing for every code commit. How would you set it up?


