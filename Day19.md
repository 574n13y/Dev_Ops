# Day 19

1. **Linux**: Change file permissions with `chmod`. What does `chmod 644 file.txt` do?
   - `chmod 644 file.txt` sets permissions on `file.txt` so that:
    - The owner has **read and write** permissions.
    - Group members have **read-only** permissions.
    - Others also have **read-only** permissions.
   - This is a common permission setting for files that should be editable by the owner but readable by others.


2. **Networking**: Explain DNS. How does it resolve domain names?
   - DNS (Domain Name System) translates human-readable domain names (like `example.com`) into IP addresses that computers use to identify each other on the network.
   - When a user enters a URL, the DNS resolver (usually maintained by the ISP or a public DNS provider) queries DNS servers to find the IP address. The resolver checks several sources: first, local cache; if not found, the resolver queries authoritative DNS servers in a hierarchy until the domain’s IP is located, allowing the user’s device to connect to the correct server.


3. **Cloud Computing**: Explain the purpose of Availability Zones.
   - Availability Zones (AZs) are isolated data center regions within a cloud provider’s infrastructure, designed to provide redundancy and fault tolerance. Each AZ operates independently, so if one AZ goes down due to failure or disaster, others can maintain uptime. 
   - By distributing resources across multiple AZs, cloud providers improve resilience, allowing applications to stay operational even in the event of localized failures.


4. **DevOps**: What’s the difference between Continuous Integration and Continuous Deployment?
   - **Continuous Integration (CI)** is the practice of frequently merging code changes from multiple contributors into a shared repository. CI often includes automated testing to ensure that new code does not break existing functionality.
   - **Continuous Deployment (CD)** takes CI further by automatically deploying every change that passes automated tests directly to production. CD ensures that code changes are quickly and consistently delivered to end users, while CI focuses on ensuring code quality in the main branch.


5. **Tools & Technology**: Define containerization. How does Docker help?
   - Containerization is the technique of packaging applications and their dependencies into isolated units, called containers, that can run reliably across different computing environments. Containers provide lightweight, isolated environments, which differ from traditional VMs by sharing the host’s OS kernel rather than running a full OS.
   - Docker is a popular containerization platform that makes it easy to build, deploy, and manage containers. Docker enables consistent environments across development, testing, and production, helping eliminate the "works on my machine" problem.


6. **Scenario**: An application runs slowly. What initial steps would you take to investigate?
   - **Identify the Bottleneck**: Determine which part (e.g., CPU, memory, disk, network) is under strain. Use tools like `top`, `htop`, `iotop`, or monitoring solutions like Grafana.
   - **Check Application Logs**: Review logs for errors or warnings that could indicate why the application is slow.
   - **Database Performance**: If the app uses a database, check for slow queries, locking issues, or high query volume.
   - **Network Latency**: Test the network response time if the application relies on external services or APIs.
   - **Application Profiling**: Use profilers to inspect code performance and detect slow functions or memory leaks.
   - **Resource Allocation**: Confirm that the application has sufficient CPU, memory, and disk resources to handle the load.

