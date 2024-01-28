
# Serverless Spring Boot example
The goal of this sample is to demonstrate the use of the [aws-serverless-java-container](https://github.com/awslabs/aws-serverless-java-container/wiki) with [Spring MVC](https://spring.io/guides/gs/rest-service/)

The `StreamLambdaHandler` object is the main entry point for the Lambda.

The application can be deployed in an AWS account using the [Serverless Application Model](https://github.com/awslabs/serverless-application-model). The `template.yml` file in the root folder contains the application definition.

## Pre-requisites
* [AWS CLI](https://aws.amazon.com/cli/)
* [SAM CLI](https://github.com/awslabs/aws-sam-cli)
* [Maven](https://maven.apache.org/)

## Deployment
In a shell, navigate to the root folder of the repository and use the SAM CLI to build a deployable package
```shell
$ sam build
```

This command compiles the application and prepares a deployment package in the `.aws-sam` sub-directory.

To deploy the application in your AWS account, you can use the SAM CLI's guided deployment process and follow the instructions on the screen

```shell
$ sam deploy --guided
```

Once the deployment is completed, the SAM CLI will print out the stack's outputs, including the new application URL. 

```text
...
CloudFormation outputs from deployed stack
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Outputs                                                                                                                                                                                                                                                                                                                                      
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Key                 SpringBootPetStoreApi                                                                                                                                                                                                                                                                                                    
Description         URL for application                                                                                                                                                                                                                                                                                                      
Value               https://xxxxxxxxxx.execute-api.us-west-1.amazonaws.com/                                                                                                                                                                                                                                                             
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
```
You can use `curl` or a web browser to make a call to the URL. Remember to append the path name: `/hello`
```shell
$ curl https://xxxxxxxxxx.execute-api.us-west-1.amazonaws.com/hello
```
