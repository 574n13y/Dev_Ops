# Day 21

---

1. **Linux**: Use `ls -l`. What does each column mean?
   - **Linux (`ls -l`)**: The `ls -l` command lists files in long format. Here’s what each column means:
    - **Column 1**: File type and permissions (e.g., `-rw-r--r--`).
    - **Column 2**: Number of hard links.
    - **Column 3**: Owner of the file.
    - **Column 4**: Group associated with the file.
    - **Column 5**: File size in bytes.
    - **Column 6**: Last modified date and time.
    - **Column 7**: File name.


2. **Networking**: What is an IP address? Find your system's IP address.
    * ** IP address **: An IP address is a unique identifier assigned to each device connected to a network, allowing it to communicate within the network. To find your system’s IP address on Linux, use:
    - `ip a` (or `ip addr show`), which shows all network interfaces and their IPs.
    - Alternatively, `hostname -I` will directly show your IP address.


3. **Cloud Computing**: What is IaaS? Name two IaaS providers.
   -  Infrastructure as a Service (IaaS) provides virtualized computing resources over the internet. It includes services like virtual machines, storage, and networks, enabling businesses to scale infrastructure without managing physical hardware. Two popular IaaS providers are:
    - **Amazon Web Services (AWS)**
    - **Microsoft Azure**
    - **Google Cloud (GCP)**
    - ** Oracle Cloud (OCI)**


4. **DevOps**: Define CI/CD and explain the purpose of each.
   - CI/CD stands for **Continuous Integration** and **Continuous Delivery/Deployment**:
    - **CI (Continuous Integration)**: Developers regularly integrate code into a shared repository, with automated testing to detect issues early.
    - **CD (Continuous Delivery/Deployment)**: Automates the release process so that new code can be deployed to production frequently and reliably, either on demand (continuous delivery) or automatically (continuous deployment).


5. **Tools & Technology**: Install Docker and run a `hello-world` container.
   - (Docker Installation)**:
    - To install Docker:
      ```bash
      sudo apt update
      sudo apt install docker-ce docker-ce-cli containerd.io
      ```
    - After installation, run the `hello-world` container to confirm Docker is working:
      ```bash
      sudo docker run hello-world
      ```
    - This command downloads a test image and runs it in a container, printing a message if successful.


6. **Scenario**: A team needs to share files on a server. Which permissions would you set up?

