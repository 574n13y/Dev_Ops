# Day 18

1. **Linux**: Use the `chmod` command to change permissions on a file. What does `chmod 755 filename` do?
   - The `chmod` command modifies file permissions. Running `chmod 755 filename` sets the permissions as follows:
     - `7` for the owner (read, write, execute)
     - `5` for the group (read and execute only)
     - `5` for others (read and execute only)
   - This means the owner can read, write, and execute the file, while group members and others can only read and execute it.


2. **Networking**: What is an IP address? How do you find your IP address in a Linux terminal?
   - An IP address is a unique identifier assigned to devices on a network to enable communication between them. In a Linux terminal, you can find your IP address using commands like:
     ```bash
     ifconfig      # older systems
     ip a          # modern systems
     hostname -I   # quick display of IP address
     ```
   - These commands display network configuration details, including IP addresses.


3. **Cloud Computing**: What are Availability Zones? How do they help with fault tolerance in cloud environments?
   - **Availability Zones (AZs)** are distinct, isolated data centers within a specific cloud region, designed to provide high availability and fault tolerance. Resources are spread across multiple AZs to prevent a single point of failure. For example, if one AZ experiences a power outage, resources in other AZs remain unaffected, ensuring resilience.


4. **DevOps**: Define Continuous Delivery and compare it with Continuous Integration.
   - **Continuous Integration (CI)** involves frequently integrating code changes into a shared repository, followed by automated testing to detect issues early.
   - **Continuous Delivery (CD)** is an extension of CI, ensuring code is always ready for deployment through automated testing, though the actual deployment to production may require manual approval.
   - In short, CI focuses on integrating and testing code frequently, while CD aims to keep the software deployable at any time.


5. **Tools & Technology**: What is Kubernetes? Set up a local Kubernetes cluster using Minikube or kind.
   - **Kubernetes** is an open-source platform for automating deployment, scaling, and management of containerized applications.
   - To set up a local Kubernetes cluster, you can use **Minikube** or **kind**:
    - **Minikube**: Creates a local cluster by starting a single-node Kubernetes environment in a virtual machine.
       ```bash
       minikube start
       ```
    - **kind**: Runs Kubernetes clusters in Docker containers, useful for testing.
       ```bash
       kind create cluster
       ```

6. **Scenario**: You are tasked with automating a daily report generation process. How would you design a simple pipeline for this?
   - To automate a daily report generation process, design a simple pipeline as follows:
    1. **Scheduler**: Use a tool like `cron` to trigger the pipeline daily.
    2. **Data Retrieval**: Write a script (e.g., Python) to pull data from sources (databases, APIs).
    3. **Data Processing**: Process the data (cleaning, aggregating) as needed.
    4. **Report Generation**: Generate the report in a preferred format (CSV, PDF).
    5. **Storage & Distribution**: Save the report and send it via email or store it in a shared location.
    6. **Logging & Notifications**: Log the process and send notifications in case of failure.
