# Day 85

1. **Linux**: Investigate memory usage with `free` and `vmstat`.
   - Monitoring system memory is essential for optimizing performance.
   - **`free -m`**: Shows memory usage in MB, including total, used, and available memory.
   - **`vmstat -s`**: Summarizes memory, CPU, and swap usage.
   - **`vmstat 2 5`**: Monitors memory and CPU every 2 seconds for 5 iterations.

   **Example:**
     ```sh
     free -h
     vmstat 2 5
     ```
   - These commands help detect memory bottlenecks and optimize system performance.

2. **Networking**: Explain CDN and its role in reducing latency.
   - A **Content Delivery Network (CDN)** is a globally distributed network of servers that caches content closer to users.
   - **Reduces Latency**: By serving content from the nearest edge location.
   - **Improves Availability**: Load distribution across multiple servers.
   - **Enhances Security**: Protects against DDoS attacks.

   **Example in AWS:**  
   AWS **CloudFront** caches website assets at edge locations, reducing the load on the origin server.

3. **Cloud Computing**: Describe AWS Lambda and its event-driven execution.
   - AWS **Lambda** is a serverless computing service that runs code in response to events.
   - **Event-Driven**: Triggers include S3 uploads, API Gateway requests, DynamoDB changes, and CloudWatch events.
   - **Scalability**: Automatically scales with demand.
   - **Pay-as-You-Go**: Charges are based on execution time.

   **Example:**  
   A Lambda function can automatically process new files uploaded to an S3 bucket.

4. **DevOps**: Define "serverless" and discuss its benefits.
   - **Serverless computing** means running applications without managing infrastructure. It abstracts server provisioning, scaling, and maintenance.

   **Benefits of Serverless:**
   - **No Server Management**: Focus on code, not infrastructure.
   - **Automatic Scaling**: Adapts to workload changes.
   - **Cost-Efficient**: Pay only for execution time.
   - **Resilience**: Built-in fault tolerance.

   **Example:**  
   AWS Lambda, Azure Functions, and Google Cloud Functions enable serverless architectures.

5. **Tools & Technology**: Create a Lambda function to process S3 file uploads.
   **Steps:**
   1. **Create an S3 Bucket** to store files.
   2. **Write a Lambda Function** in Python.
   3. **Set Up an S3 Event Trigger** to invoke the function on new uploads.
   4. **Assign IAM Roles** for S3 read access.

   **Python Code for Lambda (`lambda_function.py`):**
     ```python
     import json
     import boto3

     def lambda_handler(event, context):
         s3 = boto3.client('s3')

         for record in event['Records']:
             bucket = record['s3']['bucket']['name']
             key = record['s3']['object']['key']
             print(f"New file detected: s3://{bucket}/{key}")

         return {
             'statusCode': 200,
             'body': json.dumps('File processed successfully!')
         }
     ```
   - **Deploy Lambda** in AWS with an S3 trigger.
   - **IAM Role**: Grant permissions to read from S3.

6. **Scenario**: Implement a function that automatically processes new files in S3.
   To automate processing:
   1. **Create an S3 bucket** (`my-data-bucket`).
   2. **Deploy an AWS Lambda function** to process new files.
   3. **Configure S3 Event Notifications** to trigger Lambda on `s3:ObjectCreated:*`.
   4. **Assign IAM Role** to Lambda with `s3:GetObject` permission.
   5. **Test by uploading a file** to S3 and verifying the Lambda logs.

   **Infrastructure as Code (Terraform):**
     ```hcl
     resource "aws_lambda_function" "s3_processor" {
       function_name = "s3FileProcessor"
       runtime       = "python3.9"
       handler       = "lambda_function.lambda_handler"
       role          = aws_iam_role.lambda_role.arn
       filename      = "lambda.zip"
     }
     ```
   This solution ensures automated, scalable, and serverless processing of S3 files.
