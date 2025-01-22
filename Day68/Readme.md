# Day 68


1. **Linux**: Practice creating and restoring backups using `tar`.
#### **Creating a Backup**:
```bash
tar -cvf backup.tar /path/to/directory
```
- **Options**:
  - `c`: Create an archive.
  - `v`: Verbose mode (displays files being added).
  - `f`: Specifies the filename of the archive.

#### **Restoring a Backup**:
```bash
tar -xvf backup.tar -C /path/to/restore/location
```
- **Options**:
  - `x`: Extract files from the archive.
  - `C`: Specifies the directory to restore files to.


2. **Networking**: What is IPsec, and where is it commonly used?
#### **Definition**:
- **IPsec (Internet Protocol Security)**: A suite of protocols that secures IP communication by encrypting and authenticating packets.

#### **Key Features**:
- **Encryption**: Protects data from eavesdropping.
- **Authentication**: Verifies data origin and integrity.
- **Modes**:
  - **Transport Mode**: Encrypts the payload only.
  - **Tunnel Mode**: Encrypts the entire IP packet.

#### **Common Use Cases**:
- VPNs (Virtual Private Networks).
- Secure communication between cloud resources.
- Protecting sensitive data in transit.


3. **Cloud Computing**: Explain the role of CloudFront in AWS.
#### **What is CloudFront?**
- **Amazon CloudFront**: A Content Delivery Network (CDN) that delivers data, videos, applications, and APIs to users globally with low latency.

#### **Key Features**:
- **Edge Locations**: Cached content is served from locations closer to users.
- **Security**: Integrates with AWS Shield, AWS WAF, and SSL/TLS.
- **Dynamic Content**: Optimizes dynamic and static content delivery.

#### **Use Cases**:
- Streaming media.
- Accelerating websites.
- Distributing APIs globally.


4. **DevOps**: Describe infrastructure monitoring and key metrics to monitor.
#### **Infrastructure Monitoring**:
- **Definition**: The process of tracking the performance, availability, and health of infrastructure components (e.g., servers, databases, network devices).

#### **Key Metrics**:
- **Compute**:
   - CPU usage.
   - Memory utilization.
- **Storage**:
   - Disk I/O.
   - Free space.
- **Network**:
   - Bandwidth usage.
   - Packet loss.
- **Application**:
   - Response times.
   - Error rates.

#### **Best Practices**:
- Use tools like Prometheus, Datadog, or CloudWatch.
- Set up alerts for critical thresholds.


5. **Tools & Technology**: Configure CloudFront with an S3 bucket origin.
#### **Steps**:
- **Create an S3 Bucket**:
   - Ensure the bucket's objects have public read permissions.
- **Upload Content**:
   - Add static files (HTML, CSS, JS) to the bucket.
- **Set Up CloudFront**:
   - Specify the S3 bucket as the origin.
   - Configure cache behavior (e.g., TTL).
- **Use a Custom Domain (Optional)**:
   - Associate an SSL certificate via AWS Certificate Manager.
- **Access the Distribution**:
   - Use the CloudFront URL to test content delivery.


6. **Scenario**: Your web application needs global content distribution. How would you set it up?
#### **Solution**:
- **Use Amazon CloudFront**:
   - Distribute static assets via edge locations globally.
- **Configure an Origin**:
   - Use an S3 bucket for static content or an EC2 instance for dynamic content.
- **Secure the Setup**:
   - Enable HTTPS with SSL/TLS.
   - Use AWS WAF to protect against malicious traffic.
- **Optimize Performance**:
   - Set appropriate caching policies (e.g., time-to-live values).
- **Test the Setup**:
   - Verify performance improvements with users in different regions.


