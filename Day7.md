# Day 7

🔸 AWS Question:
How do you automate the creation and testing of AMI backups in AWS? What services would you use to ensure automated and reliable backup processes?
- To **automate the creation and testing of AMI backups**:
1. **Use AWS Backup:** Configure backup plans to automate the creation of AMIs on a schedule. AWS Backup manages policies and retention automatically.
2. **Amazon EventBridge + AWS Lambda:** Schedule Lambda functions using EventBridge (formerly CloudWatch Events) to create AMIs regularly and test restores.
3. **Automated Testing:** Use **AWS EC2 Image Builder** to build, customize, and test AMIs as part of a continuous pipeline.
4. **Lifecycle Policies:** Apply policies to manage retention and deletion of old AMIs, ensuring a reliable and automated backup process.


🔸 Linux Question:
What is the difference between grep and awk? When would you use one over the other for text processing?

🔸 Networking Question:
What is ARP (Address Resolution Protocol), and how does it work in a network to resolve IP addresses to MAC addresses?

🔸 DevOps Question:
What is a Canary Deployment, and how does it minimize the risk of rolling out new features or updates in production?

