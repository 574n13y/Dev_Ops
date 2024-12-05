# Day 33



1. **Linux**: Understand `chown` and change file ownership.
   - **`chown` Syntax:**
       ```bash
       chown [OPTIONS] USER[:GROUP] FILE
       ```
   - **Examples:**
    - Change file owner:
      ```bash
      sudo chown user1 file.txt
      ```
    - Change owner and group:
      ```bash
      sudo chown user1:group1 file.txt
      ```
    - Recursively change ownership:
      ```bash
      sudo chown -R user1:group1 /path/to/directory
      ```

   - **Why It’s Important:**
    - Controls file access by defining ownership.
    - Helps maintain security and permissions in multi-user environments.


2. **Networking**: Explain OSI Model layers.
    - The **OSI (Open Systems Interconnection)** model has 7 layers:

     | Layer       | Function                                       | Protocols/Examples       |
     |-------------|------------------------------------------------|--------------------------|
     | **7. Application** | User interface and services             | HTTP, FTP, SMTP          |
     | **6. Presentation** | Data translation and encryption        | SSL/TLS, JPEG, MPEG      |
     | **5. Session**     | Establish/manage/terminate sessions     | NetBIOS, RPC             |
     | **4. Transport**   | Reliable data transfer (TCP/UDP)        | TCP, UDP                 |
     | **3. Network**     | Routing and addressing                 | IP, ICMP, ARP            |
     | **2. Data Link**   | Frames and MAC addressing               | Ethernet, Wi-Fi          |
     | **1. Physical**    | Transmission of raw bits               | Cables, Hubs, NIC        |

   - **Key Insight:**
    - Helps understand how data flows from applications to physical devices and vice versa.


3. **Cloud Computing**: Set up a simple Lambda function.
   1. **Create a Lambda Function (AWS Console):**
    - Go to **AWS Lambda** > Create function > **Author from scratch**.
   - Fill in:
    - Function name: `MyLambdaFunction`
    - Runtime: `Python 3.x` or preferred language.
   - Add a simple handler:
     ```python
     def lambda_handler(event, context):
         return {
             'statusCode': 200,
             'body': 'Hello from Lambda!'
         }
     ```

   2. **Test the Function:**
    - Click **Test**, create a sample test event, and verify the response.

   3. **Deploy via CLI (Optional):**
    - Use `aws lambda create-function` or `update-function-code`.


4. **DevOps**: Describe a build pipeline and how it works.
   - **Definition:** Automates code compilation, testing, and deployment.
   - **Stages:**
    1. **Source:** Pull code from a repository (e.g., Git).
    2. **Build:** Compile code and resolve dependencies.
    3. **Test:** Run unit, integration, and other tests.
    4. **Release:** Package and deploy the application.
    5. **Deploy:** Deploy to staging or production environments.

   - **Tools:**
    - CI/CD platforms like Jenkins, GitLab CI, or GitHub Actions.


5. **Tools & Technology**: Use Terraform to create an EC2 and a security group.

6. **Scenario**: A client needs an autoscaling app. How would you set this up?

