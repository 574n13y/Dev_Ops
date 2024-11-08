# Day17

1. **Linux**: Use the `ls` command to list files in a directory. What does the `-l` option add to the output?

 🔹. The `ls` command lists files in a directory. Adding the `-l` option provides a long listing format, which includes more detailed information about each file, such as file permissions, number of links, owner, group, size, and timestamp of the last modification.

2. **Networking**: Explain the OSI model. Which layer does HTTP operate on?

 🔹. The OSI (Open Systems Interconnection) model is a conceptual framework used to understand network interactions in seven layers:
   - Layer 1: **Physical** – Deals with hardware transmission of raw bit streams.
   - Layer 2: **Data Link** – Manages node-to-node data transfer and error detection.
   - Layer 3: **Network** – Responsible for routing, forwarding, and addressing (e.g., IP).
   - Layer 4: **Transport** – Manages end-to-end communication and data flow (e.g., TCP, UDP).
   - Layer 5: **Session** – Manages sessions or connections between applications.
   - Layer 6: **Presentation** – Translates data formats and encrypts/decrypts data.
   - Layer 7: **Application** – Provides application-level services and network access for end-users.
   
   HTTP operates on the **Application layer** (Layer 7).

3. **Cloud Computing**: What is IaaS? Name three popular IaaS providers and their core services.

 🔹. IaaS (Infrastructure as a Service) is a cloud computing model where a provider hosts virtualized resources (servers, storage, networking) on behalf of customers, enabling them to build and manage applications without owning hardware. Three popular IaaS providers are:
   - **Amazon Web Services (AWS)**: Core services include EC2 (compute), S3 (storage), and VPC (networking).
   - **Microsoft Azure**: Core services include Virtual Machines, Blob Storage, and Virtual Network.
   - **Google Cloud Platform (GCP)**: Core services include Compute Engine, Cloud Storage, and Virtual Private Cloud.

4. **DevOps**: Explain the concept of Continuous Integration. Why is it important?

 🔹. Continuous Integration (CI) is a practice where developers frequently merge their code changes into a central repository. Each change is automatically tested, ensuring integration issues are detected early. CI is important as it promotes quick detection of defects, reduces integration problems, and accelerates the release process.

5. **Tools & Technology**: What is Docker? Install Docker on your system and run a simple `hello-world` container.

 🔹. Docker is a platform for developing, shipping, and running applications in containers, which are lightweight, isolated environments. To install Docker and run a `hello-world` container, you can:
   - **Install Docker** by following the instructions from the [Docker official documentation](https://docs.docker.com/get-docker/).
   - **Run a container**: Use the command `docker run hello-world` to download and start the `hello-world` container, which confirms Docker is installed and running correctly.

6. **Scenario**: You need to troubleshoot an application that’s not accessible from outside the network. What steps would you take to diagnose the issue?
 
🔹. To troubleshoot an application that isn’t accessible externally, you could:
   - **Verify the network connectivity** by checking if you can reach the server with `ping` or `traceroute`.
   - **Check firewall rules** to ensure external requests are allowed on the relevant port.
   - **Verify application status** to ensure it’s running by using commands like `ps`, `systemctl status`, or `docker ps` if in a container.
   - **Inspect logs** for errors in the application or network logs.
   - **Test the port** directly with tools like `telnet` or `netcat` to confirm if it’s listening.
   - **Check DNS settings** to make sure the domain resolves correctly if using a domain name.
