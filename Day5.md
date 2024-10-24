# Day 5

🔸 AWS Question:
What are AWS Security Groups, and how do they differ from Network ACLs (NACLs)?
- **Security Groups:** Act as virtual firewalls for EC2 instances, controlling inbound and outbound traffic at the instance level. They are **stateful**, meaning if a connection is allowed in one direction, the return traffic is automatically allowed.
- **Network ACLs (NACLs):** Operate at the subnet level and control traffic in and out of a subnet. They are **stateless**, meaning both inbound and outbound rules need to be explicitly defined.
- **Difference:** Security Groups are instance-specific and stateful, while NACLs are subnet-specific and stateless, providing an additional layer of network security.


🔸 Linux Question:
What is the purpose of the sudo command in Linux? How does it differ from logging in directly as the root user?

🔸 Networking Question:
What is a traceroute, and how does it help diagnose network issues? What’s the difference between ping and traceroute?

🔸 DevOps Question:
How do you handle secrets and sensitive data in a CI/CD pipeline to ensure security during deployment?

