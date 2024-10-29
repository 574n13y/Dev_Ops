# Day 11 

🔸 AWS Question:
What is AWS Elastic Beanstalk, and how does it simplify the process of deploying and scaling web applications?
- AWS Elastic Beanstalk is a Platform as a Service (PaaS) that simplifies deploying, managing, and scaling web applications. It abstracts infrastructure management by automatically handling capacity provisioning, load balancing, and scaling, allowing you to focus on code rather than infrastructure.

🔸 Linux Question:
How would you find the 10 largest files in a directory and its subdirectories on a Linux system? What command would you use?
- To find the 10 largest files in a directory and its subdirectories, use:
```bash
find /path/to/directory -type f -exec du -h {} + | sort -rh | head -10
```

🔸 Networking Question:
What is MTU (Maximum Transmission Unit), and how does it affect network performance? How would you troubleshoot MTU-related issues?
- MTU (Maximum Transmission Unit) is the largest data packet size that can be sent over a network. If the MTU is too large for the network, it may cause fragmentation, affecting performance. To troubleshoot, adjust MTU size and use commands like `ping` with the `-f` and `-s` options to test packet sizes.


🔸 DevOps Question:
What is the concept of "Shift Left" in DevOps, and how does it help improve the quality and security of software?


