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
- **`grep`:** Primarily used for searching and filtering text. It matches patterns in a file or output and displays matching lines. Best for quick searches.
- **`awk`:** More powerful for text processing. It can search, extract, and manipulate data from text files, perform calculations, and format output. Ideal for more complex data transformations.
- **When to Use:** Use `grep` for simple text searches and `awk` when you need to process and manipulate text data (e.g., extracting specific columns).


🔸 Networking Question:
What is ARP (Address Resolution Protocol), and how does it work in a network to resolve IP addresses to MAC addresses?
- **ARP (Address Resolution Protocol):** A protocol used to map an IP address to a MAC (hardware) address on a local network.
- **How It Works:** When a device wants to communicate with another on the same network, it sends out an ARP request asking "Who has this IP?" The device with the matching IP responds with its MAC address. The requesting device then uses this MAC address to send data directly.
- **Purpose:** It allows communication within a local network by resolving IP addresses to physical (MAC) addresses, ensuring proper data packet delivery.


🔸 DevOps Question:
What is a Canary Deployment, and how does it minimize the risk of rolling out new features or updates in production?
- A **Canary Deployment** is a strategy that involves rolling out new features or updates to a small subset of users (the "canary") before deploying it to the entire user base.
- **How It Minimizes Risk:** By gradually exposing the new version, you can monitor for issues, performance drops, or unexpected behavior. If the deployment is successful, it can be rolled out to more users. If not, it’s easier to roll back the change, minimizing the impact on production.


