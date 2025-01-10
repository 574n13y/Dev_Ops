# Day 57



1. **Linux**: Configure environment variables in Linux.
   - In Linux, environment variables are used to store system-wide settings and can be accessed by applications or scripts running in the system. To configure environment variables:
    - **Temporary Environment Variable** (valid only for the session):
      ```bash
      export MY_VARIABLE="value"
      ```
      This will set the variable for the current session only.
   
    - **Permanent Environment Variable**:
    1. Open the appropriate shell configuration file (e.g., `.bashrc` or `.bash_profile` for Bash users).
    2. Add the following line at the end of the file:
        ```bash
        export MY_VARIABLE="value"
        ```
    3. Save the file and reload the configuration by running:
        ```bash
        source ~/.bashrc
        ```


2. **Networking**: Explain what a CDN is and how it improves performance.

3. **Cloud Computing**: Describe the benefits of serverless architectures.

4. **DevOps**: Explain Infrastructure as Code (IaC) and its benefits.

5. **Tools & Technology**: Write a Terraform script to create a simple S3 bucket.

6. **Scenario**: Your application requires static file storage. What options does AWS provide?


