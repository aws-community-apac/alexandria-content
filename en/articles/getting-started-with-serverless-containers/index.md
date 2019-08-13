## Running your Applications in Serverless Containers

Containers improve the predictability of the behavior of the application in your local, staging, and production environments. It allows you to abstract and group your application services together and scale certain parts of your application by maximizing the distributed nature of the architecture. With containers, instead of launching several underutilized EC2 instances, we can have multiple containers inside a single EC2 instance and modify the resource requirements of each container. For example, if you have 5 running tasks, you can have 5 containers running at the same time inside 1 or 2 EC2 instances and you can manage the execution of those containers separately in their execution environments. 

### Advantage of going serverless with serverless containers

Container technology is a big topic of its own so we'll just focus on the ways on how to provide serverless solutions to manage custom containers. What do we mean by serverless containers? This means that users do not need to worry about the infrastructure underneath (EC2 instances) when running these containers. In the past, EC2 instances need to be launched first (i.e. Elastic Beanstalk, ECS without Fargate) where the containers will reside. Unfortunately, managing these instances even if minimal still introduce some operational overhead especially when dealing with scaling, security, and instance usage. 

In this article we will introduce 2 ways to run serverless containers

### AWS Fargate

With **AWS ECS - Fargate**, you don't need to worry about running your tasks inside **EC2 instances**. The `infrastructure underneath is abstracted and you just have to worry about your custom business logic inside your container`. 

The options with ECS will be pretty much the same except during the execution of the task. **Amazon Elastic Container Service** makes use of clusters, services, tasks, and task definitions where the properties of containers being executed are set. Like any kind of container management service, execution resource parameters (i.e. task size memory and task CPU) are set along with the process to be executed.

With **Fargate**, you can run a task without worrying about the management of **EC2 instances**.

### AWS Code Build

**CodeBuild** is usually used along with **CodePipeline** as the build service but it can technically run on its own. You can run any scripts and containers inside it due to the level of control possible using the service. There is an `option to run it with custom containers by making use of the Elastic Container Registry`. You pay for the build minute and you won't have to worry about spinning up an EC2 instance. Similar to **Fargate** execution resource parameters (i.e. task size memory and task CPU) are set along with the process to be executed.

As long as you are familiar with the container procedures (i.e. preparing a container and uploading to a container registry), getting started with the serverless container services should be a breeze. Majority of the immediate options are available in the interface or via the documentation and making use of these services also allow you to manage these services automatically via the **API** (i.e. Python boto3) or the **CLI**. All the other services that help users manage their applications are integrated automatically as well such as CloudWatch Logs for logging purposes and Identity and Access Management for security.
