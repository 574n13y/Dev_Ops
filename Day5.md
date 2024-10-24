# Day 5

🔸 AWS Question:
What are AWS Security Groups, and how do they differ from Network ACLs (NACLs)?
- **Security Groups:** Act as virtual firewalls for EC2 instances, controlling inbound and outbound traffic at the instance level. They are **stateful**, meaning if a connection is allowed in one direction, the return traffic is automatically allowed.
- **Network ACLs (NACLs):** Operate at the subnet level and control traffic in and out of a subnet. They are **stateless**, meaning both inbound and outbound rules need to be explicitly defined.
- **Difference:** Security Groups are instance-specific and stateful, while NACLs are subnet-specific and stateless, providing an additional layer of network security.


🔸 Linux Question:
What is the purpose of the sudo command in Linux? How does it differ from logging in directly as the root user?
- **`sudo`:** Allows a permitted user to run commands as the superuser (root) or another user, based on configuration.
- **Difference from Root Login:** Using `sudo` provides temporary elevated permissions, enabling users to perform admin tasks without needing to log in as root. It improves security by limiting root access and logging command usage.


🔸 Networking Question:
What is a traceroute, and how does it help diagnose network issues? What’s the difference between ping and traceroute?
- **Traceroute:** A network diagnostic tool that shows the path packets take from the source to the destination, listing each hop (router) along the way. It helps identify where delays or issues occur in the network.
- **Ping vs. Traceroute:** `Ping` checks connectivity by sending packets to a target and measuring the round-trip time. `Traceroute` goes further by showing the path and each hop, helping pinpoint where network issues might be occurring.

🔸 DevOps Question:
How do you handle secrets and sensitive data in a CI/CD pipeline to ensure security during deployment?

