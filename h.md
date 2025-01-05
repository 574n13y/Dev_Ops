# Day 56

1. **Linux**: Use `grep` with regex for advanced text searching.
   * The `grep` command is a powerful tool for searching text using patterns. With regular expressions (regex), you can perform advanced search operations. Examples:  
    - **Search for lines starting with "error":**  
      ```bash
      grep '^error' log.txt
      ```
    - **Find lines ending with ".com":**  
      ```bash
      grep '\.com$' file.txt
      ```
    - **Match lines containing a phone number pattern (123-456-7890):**  
      ```bash
      grep -E '[0-9]{3}-[0-9]{3}-[0-9]{4}' file.txt
      ```
    - **Search recursively in a directory:**  
      ```bash
      grep -r 'pattern' /path/to/directory
      ```


2. **Networking**: Explain the OSI model, especially Layers 4 and 7.
   - **Layer 4: Transport Layer**
    - Responsible for end-to-end communication and data delivery.
    - Protocols: TCP (reliable), UDP (unreliable but faster).
    - Key functions: Segmentation, error handling, and flow control.
    - Example: Ensuring a video stream is uninterrupted.
   
   - **Layer 7: Application Layer**
    - Closest to the end user and responsible for network services like email, file transfer, and web browsing.
    - Protocols: HTTP, HTTPS, SMTP, FTP, DNS.
    - Example: Serving web content when a URL is accessed.


3. **Cloud Computing**: Define AWS Lambda and its use cases.
   * AWS Lambda is a serverless compute service that automatically runs your code in response to triggers, eliminating the need to provision servers.  
   - **Features:**
    - Pay-per-execution model (only charged for compute time).
    - Supports multiple languages: Python, Node.js, Java, Go, etc.
    - Integrates with other AWS services (S3, DynamoDB, API Gateway).

   - **Use Cases:**
    - **API Backends:** Respond to API requests using Lambda and API Gateway.
    - **Data Processing:** Process files in S3 or streams in DynamoDB or Kinesis.
    - **Automation:** Run periodic tasks using CloudWatch Events.
    - **Event-Driven Applications:** Trigger functions based on events like database changes.


4. **DevOps**: Discuss the pros and cons of serverless computing.
   - **Pros:**
    - **Scalability:** Automatically scales with demand.
    - **Cost-Effective:** No idle server costs; pay only for usage.
    - **Reduced Ops Overhead:** No server management required.
    - **Faster Development:** Focus on code, not infrastructure.
   
   - **Cons:**
    - **Cold Start Latency:** Initial execution may be delayed.
    - **Vendor Lock-In:** Limited to the features provided by the serverless platform.
    - **Limited Runtime:** Functions have execution time limits (e.g., 15 minutes in AWS Lambda).
    - **Complex Debugging:** Distributed nature can complicate debugging and logging.


5. **Tools & Technology**: Deploy a simple AWS Lambda function.
   * **Steps to Deploy a Lambda Function:**
   1. **Create the Function:**
    - Use AWS Management Console or CLI.
    - Example Python function to log messages:
     ```python
     import json
     
     def lambda_handler(event, context):
         print("Event Received: ", event)
         return {
             'statusCode': 200,
             'body': json.dumps('Hello from Lambda!')
         }
     ```
   2. **Package the Code:**
    - ZIP the code and any dependencies:
     ```bash
     zip lambda_function.zip lambda_handler.py
     ```
   3. **Deploy the Function:**
    - Upload it to the AWS Lambda console or use the CLI:
     ```bash
     aws lambda create-function \
       --function-name MyLambdaFunction \
       --runtime python3.9 \
       --role arn:aws:iam::account-id:role/execution-role \
       --handler lambda_handler.lambda_handler \
       --zip-file fileb://lambda_function.zip
     ```
   4. **Add a Trigger:**
    - Configure triggers like an S3 bucket, API Gateway, or DynamoDB table.
 

6. **Scenario**: You need a low-cost, scalable solution for a simple API. Would Lambda be suitable?

