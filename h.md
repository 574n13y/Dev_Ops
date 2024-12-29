# Day 51

1. **Linux**: Use mount and umount to mount and unmount filesystems.
   - **Mounting**:
    - The `mount` command is used to attach a filesystem to a specific directory (known as a mount point) in the Linux filesystem hierarchy.
    - Example:
    ```bash
    sudo mount /dev/sdb1 /mnt/mydrive
    ```
    Here:
    - `/dev/sdb1` is the device or partition you want to mount.
    - `/mnt/mydrive` is the directory where the filesystem will be accessible.

   - To mount with options (e.g., read-only):
    ```bash
    sudo mount -o ro /dev/sdb1 /mnt/mydrive
    ```

   - **Unmounting**:
    - The `umount` command detaches a mounted filesystem.
    - Example:
      ```bash
      sudo umount /mnt/mydrive
      ```
      Alternatively, you can use the device name:
      ```bash
      sudo umount /dev/sdb1
      ```


2. **Networking**: Explain ARP (Address Resolution Protocol) and its role in networking.
   - **What is ARP?**
    - ARP is a protocol used to map an IP address to a MAC (Media Access Control) address on a local area network.
    - It ensures that devices can communicate with each other on the same subnet.

   - **How it works**:
    - When a device wants to send data to another device on the same subnet, it sends an ARP request asking, "Who has this IP address?"
    - The device with the matching IP replies with its MAC address.
    - The requesting device then uses this MAC address to send the data at the data link layer.

   - **Role in Networking**:
    - ARP resolves IP addresses to MAC addresses, which are required for Ethernet-based communication.
    - It is critical in ensuring proper routing of packets within local networks.



3. **Cloud Computing**: Describe the process of creating a custom AMI.
    1. **Prepare the Instance**:
    - Launch an EC2 instance with the desired OS and configurations.
    - Install required software, packages, or make customizations.
    2. **Clean Up the Instance**:
    - Remove temporary files, logs, and sensitive data.
    - Stop unnecessary services to reduce the AMI size.
    3. **Create the AMI**:
    - Use the AWS Management Console or CLI to create the AMI:
      ```bash
      aws ec2 create-image --instance-id <instance_id> --name "<ami_name>" --description "<description>"
      ```
    - This will create an AMI that can be used to launch instances with the same configuration.
    4. **Verify the AMI**:
    - Launch a new instance using the custom AMI to ensure that everything works as expected.



4. **DevOps**: What is continuous deployment, and how is it implemented?
   - **What is Continuous Deployment?**
    - Continuous deployment is the practice of automatically deploying every change that passes automated tests into production.
    - It eliminates manual approvals, focusing instead on rigorous automated testing.

  - **Implementation Steps**:
   1. **Version Control**:
    - Use Git or similar tools to track changes in the application code.
   2. **Automated Builds**:
    - Use CI/CD tools like Jenkins, GitLab CI, or GitHub Actions to build the application automatically when changes are pushed.
   3. **Automated Testing**:
    - Implement unit, integration, and system tests.
    - If all tests pass, the pipeline proceeds to deployment.
   4. **Automated Deployment**:
    - Use deployment tools (e.g., Kubernetes, Terraform, Ansible) to roll out changes to production.

   - **Best Practices**:
    - Monitor deployments closely.
    - Use feature flags to control new features.
    - Set up rollback mechanisms in case of issues.



5. **Tools & Technology**: Set up a basic environment variable file in Ansible.
   - **Steps**:
    1. **Create a Variable File**:
    - Define your environment variables in a YAML file:
       ```yaml
       # vars/env_vars.yml
       app_name: "MyApp"
       db_host: "db.example.com"
       db_user: "admin"
       db_password: "securepassword"
       ```
    2. **Include the File in a Playbook**:
       ```yaml
       - name: Deploy application
         hosts: webservers
         vars_files:
           - vars/env_vars.yml
             tasks:
           - name: Display environment variables
             debug:
               msg: "Connecting to database {{ db_host }} as {{ db_user }}"
       ```
    3. **Run the Playbook**:
       ```bash
       ansible-playbook deploy.yml
       ```



6. **Scenario**: Your web servers need customized configurations. How would you manage this across multiple servers?


