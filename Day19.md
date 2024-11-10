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
4. **DevOps**: What’s the difference between Continuous Integration and Continuous Deployment?
5. **Tools & Technology**: Define containerization. How does Docker help?
6. **Scenario**: An application runs slowly. What initial steps would you take to investigate?


