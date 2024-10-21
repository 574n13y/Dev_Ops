# Day 3

🔸 AWS Question:
In AWS, if you have an EC2 instance in a public subnet without an Elastic IP assigned, can it access the internet?
- If an EC2 instance is in a public subnet without an Elastic IP, it can still access the internet if it is using a NAT Gateway or NAT instance. Without an Elastic IP, it won't be directly accessible from the internet, but it can initiate outbound connections via NAT.

🔸 Linux Question:
What is the difference between hard links and symbolic (soft) links in Linux? What happens to each if the original file is deleted?

1. Hard Link: Directly points to the same inode (data) as the original file. If the original file is deleted, the hard link still holds the data.
2. Symbolic (Soft) Link: A pointer to the original file's path. If the original file is deleted, the symbolic link becomes broken.

🔸 Networking Question:
What is the difference between a Layer 2 switch and a Layer 3 switch? Can a Layer 3 switch perform routing, and if so, how is it different from a traditional router?
1. Layer 2 Switch: Operates at the Data Link layer, forwarding traffic based on MAC addresses.
2. Layer 3 Switch: Operates at both Layer 2 and Layer 3, capable of routing traffic based on IP addresses.
3. Layer 3 vs. Router: A Layer 3 switch can perform routing within a LAN (faster switching), whereas traditional routers are used for inter-network routing and have more features (e.g., NAT, firewall capabilities).

🔸 DevOps Question:
In a Git workflow, what is the difference between git merge and git rebase, and how can using one over the other affect the commit history?
1. git merge: Combines branches by creating a new commit, preserving the full branch history.
2. git rebase: Moves or reapplies commits from one branch to another, creating a linear history by rewriting commit sequences.
Effect on History: Merging keeps all commits visible, while rebasing creates a cleaner, linear commit history, which can make it easier to read but may lead to conflicts if done improperly on shared branches.
