# Day 14

🔸 AWS Question:
What is an IAM policy in AWS, and how does it control access to resources? How do policies differ from roles?
- An IAM policy in AWS is a JSON document that defines permissions to access AWS resources. It specifies *who* can do *what* on *which resources*. Policies can be attached to users, groups, or roles. For example, a policy might allow an EC2 instance to access S3 buckets. *Roles* differ in that they’re assumed temporarily by entities like users or services for cross-account or service-based access, whereas policies define access permissions.

🔸 Linux Question:
What is the purpose of the ping command in Linux, and how can it help diagnose network connectivity issues?
- The `ping` command tests network connectivity between the host and a target (like an IP or domain) by sending ICMP echo requests. It helps diagnose issues like packet loss or latency by measuring the response time. For example, `ping google.com` checks if your device can reach Google’s servers.

🔸 Networking Question:
What is the role of DNS (Domain Name System) in networking, and why is it essential?
- DNS (Domain Name System) translates human-readable domain names (like `example.com`) into IP addresses, allowing browsers to load internet resources. It’s essential for seamless internet navigation; without DNS, users would need to remember IP addresses instead of domain names.

🔸 DevOps Question:
What is artifact management in DevOps, and why is it important? Can you name some popular tools for managing artifacts?
- Artifact management in DevOps involves storing, organizing, and managing binary files created during development, like `.jar` or `.zip` files. It ensures consistency across deployments. Tools like *Artifactory*, *Nexus*, and *Azure Artifacts* are popular for managing artifacts, ensuring they’re available for testing and production environments.



