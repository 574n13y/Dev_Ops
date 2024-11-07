# Day 16

1. **Linux**: What command would you use to display the current directory? Try using both absolute and relative paths.
- **Command to Display the Current Directory:**
    - To display the current working directory using an **absolute path**, use:
      ```bash
      pwd
      ```
      This shows the full path from the root (`/`) to your current directory.
    - To display it in a **relative path** form, navigate with `cd` commands (like `cd ..` to go up one level), then use `pwd` again to see the updated path relative to your starting location.

2. **Networking**: What is the purpose of the `ping` command? Test the network connection to `google.com`.
- **Purpose of the Ping Command:**
    - `ping` checks connectivity and measures the response time between your machine and a remote host. It is commonly used to verify network connections or troubleshoot network issues.
    - To test the network connection to `google.com`, use:
      ```bash
      ping google.com
      ```
      This sends ICMP (Internet Control Message Protocol) echo requests to Google and shows the latency or any potential packet loss

3. **Cloud Computing**: Explain the difference between public, private, and hybrid clouds.
- **Public, Private, and Hybrid Clouds:**
    - **Public Cloud:** Resources (like storage and servers) are owned and managed by a third-party cloud provider and made available to the general public over the internet. Examples include AWS, Google Cloud, and Azure. It’s generally cost-effective and highly scalable.
    - **Private Cloud:** This is a cloud infrastructure that an individual or organization solely owns and uses. It provides greater control over data and security but is generally more expensive and requires in-house management.
    - **Hybrid Cloud:** Combines both public and private clouds, allowing data and applications to be shared between them. It provides flexibility by moving workloads between environments, balancing security, scalability, and cost.


4. **DevOps**: Define DevOps in your own words. What are its core principles?
5. **Tools & Technology**: What is Git? Initialize a Git repository and create your first commit with a README file.
6. **Scenario**: You are asked to deploy an application in a secure, high-availability setup on a cloud platform. What key steps would you consider?


