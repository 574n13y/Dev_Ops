# Day 9

🔸 AWS Question:
What is AWS Config, and how can it be used to monitor compliance and track configuration changes across your AWS resources?
- AWS Config: AWS Config is a service that tracks and records configuration changes to your AWS resources, enabling you to assess compliance with internal policies. It continuously monitors and evaluates resource configurations, providing a history of changes and generating alerts if configurations drift from the desired state.


🔸 Linux Question:
Explain the difference between ps and top commands in Linux. When would you prefer using one over the other?
- ps vs. top:

1. ps shows a snapshot of currently running processes at a specific moment, useful for seeing detailed information about specific processes.
2. top is a real-time, dynamic view of system processes, continuously updating the list. It’s helpful for monitoring system performance and resource usage over time.
Use ps for a one-time check and top for continuous monitoring.



🔸 Networking Question:
What is the difference between a VLAN (Virtual Local Area Network) and a Subnet, and how do they help in network segmentation?
- VLAN: Divides a physical network into multiple logical networks, isolating traffic at the data link layer (Layer 2).
- Subnet: Partitions an IP network into smaller segments, controlling traffic at the network layer (Layer 3).
Both help in segmenting networks but at different layers, improving security and traffic management.


🔸 DevOps Question:
What are the main differences between Blue-Green Deployment and Feature Toggles?
1. **Blue-Green Deployment:** Maintains two environments (blue and green) where one is live, and the other is a staging environment. You switch traffic to the new version once it's tested and ready.
2. **Feature Toggles:** Allows deploying code with features hidden or disabled, which can be turned on or off without redeploying the application, enabling continuous delivery and feature experimentation.
