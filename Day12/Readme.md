# Day 12

🔸 AWS Question:
What is the purpose of AWS IAM roles, and how do they differ from IAM users? In what scenarios would you use an IAM role over a user?
- AWS IAM roles provide temporary permissions to AWS resources without requiring long-term credentials, unlike IAM users, which have permanent credentials. Roles are ideal for use cases like EC2 instances needing access to S3 or for cross-account access, as they allow access without storing credentials.

🔸 Linux Question:
How do you find files that have been modified in the last 7 days within a specific directory in Linux? What command would you use?
- To find files modified in the last 7 days in a specific directory, use:
```bash
find /path/to/directory -type f -mtime -7
```

🔸 Networking Question:
What is a load balancer, and how does it improve network performance? Can you explain the difference between Layer 4 and Layer 7 load balancing?
- A load balancer distributes incoming traffic across multiple servers, improving network performance and reliability. Layer 4 (transport layer) balances based on IP and TCP/UDP information, while Layer 7 (application layer) balances based on HTTP headers and content, providing more granular control.

🔸 DevOps Question:
What is the difference between observability and monitoring in DevOps? Why is observability important for modern applications?
- Monitoring tracks specific metrics (e.g., CPU, memory), while observability focuses on understanding system behavior through logs, metrics, and traces. Observability is essential for diagnosing complex issues in modern distributed systems, giving deeper insights into the "why" behind issues.

