---
Created: 2022-11-05T21:49
---
HA: Maximizing the system’s online time. It’s about fast or auto recovery when issueing.  
- Ex: Backup tire in car, fast to replace the error one.  
FT: Continue operating when failure.  
- Ex: Backup engine in airplane, fast to power up when the main engine is damaged  
DR: Enable the recovery of vital technology infrastructures.  
- Ex: Skydiving when airplane has error.  
  

Private vs Public AWS (network):  
- Normal public internet / AWS public services / AWS private cloud  
Region / AZ / Edge location  
VPC:  
- A VPN is bound within an account and a region.  
- A VPC is separated with other public services by default  
- Default VPC  
+ 1 VPN per region.  
+ VPN CIDR: 172.31.0.0/16  
+ A VPC CIDR is divided into multi subnets for each AZ.  
+ A public IPv4 address is assigned to a default VPC.  
EC2:  
- Virtual machines ~ instances are laughed into a specific subnet.  
- Default: private service mapped to a VPC.  
- AZ resilience.  
- Storage: local-host or EBS (Elastic block store).  
- Include CPU, mem, disk, and network.  
- Money charging: Running (4), Stopped (Disk), Terminated (Completely deleted, can’t revert)(0).  
- AMI (Amazon machine image):  
+ Permission: Public, Owner, Explicit.  
+ Root volume: Booting location.  
+ Block device mapping: Which one is root volume, which one is data volume  
- Connect:  
+ Different on Linux and Window  
- Instance types:  
+ On-demand:  
+ Dedicated instance: Single-tenant instance.  
+ Dedicated hosts: Allow using the existing software licenses and control how instances are placed on the server.  
- Scaling:  
+ Vertical scale: Increase GB, CPU → Limit in size, downtime, single point failure, double cabacity only,  
+ Horizontal scale: Add more instance → Aware of session (Use stateless server and store sessions on of-host database), need Load balancer  
- Key pair: Log in into instance.  
-  
S3:  
- Object storage service.  
- Object is limited to 5Tb.  
- Bucket names are globally unique.  
Cloudwatch:  
- Metrics, logs, events  
- Datapoint: timestamp + value  
NACLs:  
- Network access control lists.  
- Affect INBOUND and OUTBOUND, not within a subnet.  
- Stateless: Don’t know if the message is request or response.  
- In order, processing from the lowest rule number.  
- Each subnet can have one NACLs.  
SG:  
- Security group.  
- Stateful: auto-detect response message, allow request → allow response.  
- NO explicit deny: Only explicit allow or implicit deny.  
- Support IP/CIDR and logical resources (Can use source as another SG and also itself).  
- It’s not attached to an instance, it’s attached to the primary network interface of that instance (ENI).  
- Using SG to allow traffic and NACLs to deny traffic.  
Cognito:  
- Authentication, authorization, and user management for web/mobile applications.  
- User pools - Sign-in → get a JWT  
- Identity Pool → temporary AWS credentials  
- Unauthenticated identity → Guest  
- Federated Identity → Using 3rd party.  
SSM Parameter Store:  
- A secure and hierarchical storage for config data and secrets.  
Cloudwatch:  
- Focus on activities of AWS services → Report health and performance.  
Cloudtrail:  
- Logs API calls inside AWS and these logs are written in batch to S3 or CloudWatch  
- Need to config all-region for global services.  
- Cloudtrait can be grouped within an organization.  
- No real time since it’s a batch process.  
ECR:  
- Store, manage and deploy docker images.  
- Using config to fast deploy.  
EFS:  
- Auto scale when adding/removing files.  
-  
ECS:  
- Start, stop and manage container on clusters.  
- Fargate launch type - Pay as you go, run containers without needing to manage your infrastructure.  
Lambda:  
- Faas ~ Pass: provide runtime env.  
- Event-driven service.  
- 3secs to 15mins job timeout.  
- Specific memory, associated CPU.  
- Cloudwatch logs require permission via the execution role.  
- Version: code + configuration. $Latest, Alias  
+ Version will be created after published (Immutable, qualified ARN).  
+ If you not publish → unqualified version, mutable ARN.  
- On high load: Provisioned concurrency (Catch execution context)  
- INIT, COLD START, (TERMINATION) | WARM START, (TERMINATION)  
+ Function init: code outside lambda_handler  
+ Invoke: lambda_handler  
- Alias:  
+ Minical code change when pointing to a working version.  
+ Can be used as an ARN point to the static published version.  
+ Use weight alias to distribute between different versions.  
- Avocation:  
* Sync:  
+ CLI/API waits for lambda functions to be successful or failed.  
+ Error handling will be handled by the client.  
+ Async: AWS services  
+ Even mapping:  
+ Use lambda event source mapping to trigger lambda call from non-direct call services (KDS, SQS, DynamoDb stream)  
+ Use the same role as lambda role.  
+ Consistently failed batches will be sent to SQS or SNS topic.  
VPC  
Beanstalk:  
-  
API Gateway:  
- Manage REST operations  
- Can change the request and response template to/from the backend.  
SQS:  
- Can split unprocessed message to dead-letter queue.  
  
Loggings:  
X-Ray:  
- Distributed tracing.  
-  
  
Terms:  
- Idempotence: runs many times → same output.