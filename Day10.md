# Day 10

🔸 AWS Question:
What is AWS CloudTrail, and how does it help with auditing and monitoring AWS accounts? How do you set up CloudTrail to track changes across multiple regions?
- **AWS CloudTrail**:
AWS CloudTrail records and logs API calls made in your AWS account, providing visibility into user actions and resource changes for auditing and monitoring. To track changes across multiple regions, you can create a multi-region trail that consolidates logs from all regions into a single S3 bucket, making it easier to audit activity across your AWS environment.

🔸 Linux Question:
What is the umask command in Linux, and how does it affect file and directory permissions? How can you modify the default umask value for a user?
- `umask`**:
The `umask` command sets default permissions for newly created files and directories by specifying which permission bits to mask out. It subtracts permissions from the system default (666 for files, 777 for directories). You can modify the default `umask` value by adding a `umask` command in the user’s shell configuration file (e.g., `.bashrc` or `.profile`).

🔸 Networking Question:
What is the difference between a stateful firewall and a stateless firewall? In what scenarios would you use one over the other?
**Stateful vs. Stateless Firewall**:
- **Stateful Firewall**: Monitors and tracks the state of active connections, making decisions based on the context of traffic (e.g., allowing response packets for an initiated connection). Suitable for scenarios needing dynamic, context-aware filtering.
- **Stateless Firewall**: Inspects each packet individually without regard for connection state, useful for fast, simple filtering in high-throughput environments where basic, consistent rules are sufficient.

🔸 DevOps Question:
What is the purpose of using a reverse proxy in a microservices architecture, and how does it improve performance and security?


