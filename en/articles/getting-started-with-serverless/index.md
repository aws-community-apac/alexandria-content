# Getting Started with Serverless Applications

What's with all the hype with **serverless applications**? The **serverless movement** has challenged and transformed how software is built for the past couple of years. 

### Advantages of going Serverless
- **Faster time to ship**: Less focus on operational responsibilities to focus more on custom business logic and innovation
- **Cost Control**: Helps teams to reduce cost significantly by only paying for what you use
- **Scalability and Resiliency**: Serverless architectures utilizing managed services are essentially scalable and resilient


### How is it different from previous implementations?

#### Previous Tech Stack
```
Python + Flask
ELB
EC2
RDS
AWS OpsWorks + Chef + Ruby
CloudWatch Logs
CloudFormation
```
#### Serverless Stack
```
Python
API Gateway
AWS Lambda
DynamoDB
SAM Templates
CloudWatch Logs
CloudFormation
```

**Serverless architectures** benefit from the pay-per-use pricing model. The cost scales based on the usage rate of your application. For example, an **AWS Lambda function** that uses `128MB of memory`, you only pay for `$0.000000208 per 100ms` (North Virginia). This means that you can have a staging environment running `24/7` that looks exactly the same as with the production environment without worrying about the cost as only the developers and testers are using it. Similar pricing models are available in other services of AWS.

**Scaling** and **self-healing** are also `automatic by default` due to the constraints and assumptions of **serverless architectures**. In previous architectures, the `auto-scaling and management of instances are managed separately` through the use of configuration management tools such as **Chef**, **Puppet**, **Ansible**, and other tools. **Log management** needs to be taken care of as well to ensure that the logs are not lost during the scale down activities. There is also the `risk of teams over-engineering and spending too much resources on the operational aspects of infrastructure management` that prevents teams from focusing on business logic and software development.


### Use cases

What you can do with previous architectures, you can build with serverless architectures. For starters, you may start with applications such as:

- **Facial Recognition**: Amazon S3 + Amazon Rekognition + AWS Lambda + Amazon DynamoDB
- **GraphQL Web Endpoint**: AppSync + AWS Lambda + DynamoDB
- **Sample Translation Background Workflow**: Step Functions + Amazon Translate + AWS Lambda + Amazon DynamoDB


Feel free to get started building these applications using the `free tier`. Tutorials on how to build these applications may be presented in future blog posts so stay tuned!
