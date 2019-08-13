## Getting started with Serverless GraphQL API Endpoints

### What's GraphQL?

**GraphQL** is one of the philosophies for designing and building modern APIs. Instead of consuming rigid and strict server-defined REST API endpoints, **GraphQL** allows a certain level of flexibility with custom endpoints that transfer the control of data retrieval to the consumer side of things. One of GraphQL's main advantages is that it allows returning data usually from multiple endpoint requests in a single request. GraphQL involves a declarative type system, a schema language, and a runtime. This is not an article about GraphQL vs REST so we'll proceed with describing the serverless approach to launch GraphQL endpoints. 

### An introduction to AWS AppSync

**AWS AppSync** is AWS's serverless solution for designing and building GraphQL endpoints. Instead of worrying about the infrastructure (i.e. EC2 Instances) where the GraphQL endpoint is hosted, **AWS AppSync** abstracts a lot of things for the user and provides different configuration sections where the custom logic is placed.

- **Schema** defines the capabilities of the GraphQL API. It allows the user to shape the data that flows through the API with the schema definition language. 

- **Data Sources**, as the name suggests, are the sources where data is fetched and saved. They may be in the form of real data stores such as DynamoDB but the can also be Lambda functions. Other options are possible as well but the common examples usually involve DynamoDB as it binds well with such database option

- **Functions** and **Resolvers** serve as the glue that processes and transforms the data from the data sources and makes sure that the result matches what was defined in the schema.

### Getting started with a sample application

Getting a hello world application to run with **AWS AppSync** is easy. If you use the wizard, you'll easily be able to prepare a simple GraphQL endpoint by just following the steps. It automatically creates a DynamoDB table for you and mapping the fields to the results is simple because of the wizard. AWS automatically generates the functions and resolvers you'll need to get started and you can modify them later after the resources have been created.

To verify if the application endpoint is working, you may use the queries page or you may use Postman (or a similar tool). By specifying the API key, endpoint calls will be possible as long as the query format is followed. 

### Advantages of the Serverless approach

- As you can see, there's no EC2 instance involved and you only have to manage the custom implementations available for configuration in the AppSync API or interface. 

- Another advantage of this approach is that you only pay for what you use and you have the option to create staging environments similar to production environments without worrying about the cost for the staging environment. 


That's it! If you want to evolve and make more complex GraphQL endpoints, you may check how to use and modify Pipeline and Unit Resolvers but this should help you get started. 
