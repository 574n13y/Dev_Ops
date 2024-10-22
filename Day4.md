# Day 4

🔸 AWS Question:
What is an Elastic IP in AWS, and how does it differ from a public IP?
- An **Elastic IP** is a static, public IPv4 address that you can allocate to your AWS account and assign to an EC2 instance. Unlike a regular public IP (which is dynamic and changes if the instance is stopped and started), an Elastic IP remains the same even if the instance restarts or is reattached to a different instance. This is useful for maintaining a consistent endpoint.

🔸 Linux Question:
What command would you use to check the disk space usage on a Linux system? Can you explain how to interpret the output?
- To check disk space usage, use the command:
```bash
df -h
```
- **`df`:** Displays disk space usage.
- **`-h`:** Shows output in a human-readable format (e.g., MB, GB).
- **Output Interpretation:** The output shows each filesystem, total size, used space, available space, and usage percentage. The `Mounted on` column indicates the directory where the filesystem is mounted.

🔸 Networking Question:
What is a default gateway, and why is it important in a network?
A **default gateway** is a device (usually a router) that routes traffic from a local network to other networks (e.g., the internet). It is crucial because it allows devices on a local network to communicate with devices outside their network. Without a default gateway, devices would not know where to send data destined for external addresses.

🔸 DevOps Question:
What is the purpose of a Dockerfile, and how does it help in containerization?
A **Dockerfile** is a script containing instructions to build a Docker image. It defines the environment, dependencies, application code, and commands to run inside a container. By using a Dockerfile, you can create consistent and reproducible container images that can be deployed across different environments, helping streamline the containerization process.(concept of key and value)

