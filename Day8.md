# Day 8

🔸 AWS Question:
How do you ensure high availability of your application running in AWS across multiple regions? What AWS services can you use to achieve this?
- To ensure high availability across multiple regions, you can deploy your application using **Amazon Route 53** for DNS failover. For example, if your app is hosted in **us-east-1** and **us-west-2**, Route 53 can redirect traffic to **us-west-2** if **us-east-1** experiences downtime. Use **Elastic Load Balancing (ELB)** to distribute incoming traffic across multiple EC2 instances in each region. You can also use **Amazon RDS Multi-Region Read Replicas** to ensure database availability and **S3 Cross-Region Replication** for data consistency across regions.

🔸 Linux Question:
What is the difference between cron and at in Linux? When would you use each for task scheduling?

🔸 Networking Question:
What is the difference between NAT (Network Address Translation) and PAT (Port Address Translation)? When would you use PAT over NAT?

🔸 DevOps Question:
What is the purpose of using Helm in Kubernetes, and how does it simplify the management of Kubernetes applications?


