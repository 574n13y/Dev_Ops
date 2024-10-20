# Day 2

🔸 AWS Question:
What is an Availability Zone in AWS, and how does it differ from a Region?
- An Availability Zone (AZ) in AWS is an isolated data center within a Region. Each Region consists of multiple AZs, providing redundancy and fault tolerance. A Region is a geographical area (e.g., US East, EU Central) containing multiple AZs, allowing for distributed
🔸 Linux Question:
What does the chmod command do in Linux? How would you use it to grant execute permissions to a file?
- The chmod command in Linux changes file permissions. To grant execute permissions to a file, you can use:
```
chmod +x filename
```
```
chmod 700 filename
```
```
chmod u=x,g=r,o=w filename
```
🔸 Networking Question:
What is the difference between TCP and UDP protocols, and when would you use each?
- TCP (Transmission Control Protocol) is connection-oriented, ensuring reliable data transmission with error checking. UDP (User Datagram Protocol) is connectionless, faster, and used when speed is prioritized over reliability (e.g., streaming). Use TCP for tasks needing reliability (e.g., file transfers) and UDP for tasks requiring low latency (e.g., VoIP).
🔸 DevOps Question:
What is CI/CD in DevOps, and why is it important for modern software development and deployment?
- CI/CD stands for Continuous Integration and Continuous Deployment/Delivery. It automates the process of integrating code changes, testing, and deploying applications. This approach is crucial for modern software development, as it enables rapid, reliable, and consistent delivery of updates to production.
