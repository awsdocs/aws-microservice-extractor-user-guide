# Manually deploy as independent service<a name="microservice-extractor-deploy"></a>

To deploy parts of your application as smaller services, we recommend that you set up the following environment:
+ Docker version 17\.05 installed locally with administrator access
+ An AWS profile with an attached policy that grants permissions to write to Amazon Elastic Container Registry and Amazon S3
+ Windows Server 2019 or later
+ A minimum of 50 GB of free disk space

To deploy the extracted service as an independent service, perform the following high\-level steps:

1. Refactor the source code, if necessary, to ensure that the extracted service builds successfully\.

1. Navigate to the output location of the extracted service\.

1. From the Dockerfile, manually create a Docker container image\.

1. Push the Docker container image to Amazon Elastic Container Registry \(Amazon ECR\)\.

1. Use AWS CloudFormation to deploy the container image hosted in Amazon ECR to Amazon Elastic Container Service \(ECS\)\. For more information, see [Using Amazon ECR with Amazon ECS](https://docs.aws.amazon.com/ecr-repositories.html) and [Creating Amazon ECS resources with AWS CloudFormation](https://docs.aws.amazon.com/creating-resources-with-cloudformation.html)\.