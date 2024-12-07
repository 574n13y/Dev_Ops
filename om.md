# Day 35

1. **Linux**: Use `find` to search for files. Experiment with different flags.
   - The `find` command is a powerful tool to search for files and directories in Linux.

     **Examples:**
   - **Find files by name**:
      ```bash
      find /path/to/search -name "filename"
      ```
   - **Find files by extension**:
      ```bash
      find /path/to/search -name "*.txt"
      ```
   - **Find files modified in the last 7 days**:
      ```bash
      find /path/to/search -type f -mtime -7
      ```
   - **Find files larger than 1MB**:
      ```bash
      find /path/to/search -type f -size +1M
      ```
   - **Execute a command on found files**:
      ```bash
      find /path/to/search -name "*.log" -exec rm {} \;
      ```

Experiment with different flags like `-user`, `-group`, and `-perm` to tailor your searches.


2. **Networking**: What is a firewall? How does it work?

3. **Cloud Computing**: Discuss the benefits of Elastic Block Store (EBS) volumes.

4. **DevOps**: Explain what Git branching strategies are and why they’re useful.

5. **Tools & Technology**: Set up Git with branching. Practice merging and resolving conflicts.

6. **Scenario**: A large team works on the same codebase. What Git strategies would you recommend?


