# AWS Microservice Extractor for \.NET security<a name="microservice-extractor-security"></a>

Cloud security at AWS is the highest priority\. As an AWS customer, you benefit from data centers and network architectures that are built to meet the requirements of the most security\-sensitive organizations\. Security is a shared responsibility between AWS and you\. The [shared responsibility model](http://aws.amazon.com/compliance/shared-responsibility-model/) describes this as security of the cloud and security in the cloud: 
+ **Security of the cloud **– AWS is responsible for protecting the infrastructure that runs AWS services in the AWS Cloud\. AWS also provides you with services that you can use securely\. Third\-party auditors regularly test and verify the effectiveness of our security as part of the [AWS Compliance Programs](http://aws.amazon.com/compliance/programs/)\. For more information about the compliance programs that apply to Microservice Extractor, see [AWS Services in Scope by Compliance Program](http://aws.amazon.com/http://aws.amazon.com/compliance/services-in-scope/)\.
+ **Security in the cloud** – Your responsibility is determined by the AWS service that you use\. You are also responsible for other factors including the sensitivity of your data, your company’s requirements, and applicable laws and regulations\.

This documentation helps you understand how to apply the shared responsibility model when using AWS Microservice Extractor for \.NET\. The following topics show you how to configure Microservice Extractor to meet your security and compliance objectives\. You also learn how to use other AWS services that help you to monitor and secure your Microservice Extractor resources\.

**Topics**
+ [Data protection in AWS Microservice Extractor for \.NET](#microservice-extractor-data-protection)
+ [Identity and Access Management in AWS Microservice Extractor for \.NET](#microservice-extractor-security-iam)
+ [Configuration and vulnerability analysis in AWS Microservice Extractor for \.NET](#microservice-extractor-configuration-vulnerability-analysis)
+ [Security best practices](#microservice-extractor-security-best-practices)

## Data protection in AWS Microservice Extractor for \.NET<a name="microservice-extractor-data-protection"></a>

The AWS [shared responsibility model](http://aws.amazon.com/compliance/shared-responsibility-model/) applies to data protection in AWS Microservice Extractor for \.NET\. As described in this model, AWS is responsible for protecting the global infrastructure that runs all of the AWS Cloud\. You are responsible for maintaining control over your content that is hosted on this infrastructure\. This content includes the security configuration and management tasks for the AWS services that you use\. For more information about data privacy, see the [Data Privacy FAQ](http://aws.amazon.com/compliance/data-privacy-faq)\. For information about data protection in Europe, see the [AWS Shared Responsibility Model and GDPR](http://aws.amazon.com/blogs/security/the-aws-shared-responsibility-model-and-gdpr/) blog post on the *AWS Security Blog*\.

For data protection purposes, we recommend that you protect AWS account credentials and set up individual user accounts with AWS Identity and Access Management \(IAM\)\. That way each user is given only the permissions necessary to fulfill their job duties\. We also recommend that you secure your data in the following ways:
+ Use multi\-factor authentication \(MFA\) with each account\.
+ Use SSL/TLS to communicate with AWS resources\. We recommend TLS 1\.2 or later\.
+ Set up API and user activity logging with AWS CloudTrail\.
+ Use AWS encryption solutions, along with all default security controls within AWS services\.
+ Use advanced managed security services such as Amazon Macie, which assists in discovering and securing personal data that is stored in Amazon S3\.
+ If you require FIPS 140\-2 validated cryptographic modules when accessing AWS through a command line interface or an API, use a FIPS endpoint\. For more information about the available FIPS endpoints, see [Federal Information Processing Standard \(FIPS\) 140\-2](http://aws.amazon.com/compliance/fips/)\.

We strongly recommend that you never put confidential or sensitive information, such as your customers' email addresses, into tags or free\-form fields such as a **Name** field\. This includes when you work with Microservice Extractor or other AWS services using the console, API, AWS CLI, or AWS SDKs\. Any data that you enter into tags or free\-form fields used for names may be used for billing or diagnostic logs\. If you provide a URL to an external server, we strongly recommend that you do not include credentials information in the URL to validate your request to that server\.

**Encryption at rest**  
Data within AWS Microservice Extractor for \.NET is not encrypted at rest\.

**Encryption in transit**  
For configuration and metrics, Microservice Extractor makes requests to the server over the Transport Layer Security protocol \(TLS\)\.

### Data collected by AWS Microservice Extractor for \.NET<a name="microservice-extractor-data-protection-collected"></a>

Usage data sharing is enabled by default\. You can disable usage data sharing by clearing the check box for usage data sharing on the AWS Microservice Extractor for \.NET **Settings** page \. 

When usage data sharing is enabled, Microservice Extractor collects the following information when you onboard your source code:
+ Success/failure operations performed during onboarding, static code analysis, application build, and graph creation\.
+ Resources consumed during operations, such as CPU and memory usage\.
+ Number of nodes and dependencies\.
+ Number of detected islands\.

Microservice Extractor doesn’t collect proprietary information, such as source code\. In the case of failure, the tool might collect stack traces to improve product experience\.

## Identity and Access Management in AWS Microservice Extractor for \.NET<a name="microservice-extractor-security-iam"></a>

AWS Identity and Access Management \(IAM\) is an AWS service that helps an administrator securely control access to AWS resources\. AWS Microservice Extractor for \.NET is a standalone application that does not require IAM access control to use resources\.

To use Microservice Extractor, you must attach the policy for permissions to use the Microservice Extractor assessment tool to your IAM user\. These policies are provided in the [Prerequisites](microservice-extractor-prerequisites.md) section of this guide\.

## Configuration and vulnerability analysis in AWS Microservice Extractor for \.NET<a name="microservice-extractor-configuration-vulnerability-analysis"></a>

When AWS Microservice Extractor for \.NET requires updates, you are notified and must install the latest version of the application upon restart\. You maintain the system patching responsibility, per the [shared responsibility model](http://aws.amazon.com/compliance/shared-responsibility-model/)\.

## Security best practices<a name="microservice-extractor-security-best-practices"></a>

AWS Microservice Extractor for \.NET provides security features to consider as you develop and implement your own security policies\. The following best practice is a general guideline and doesn’t represent a complete security solution\. Because this best practice might not be appropriate or sufficient for your environment, treat it as a helpful consideration rather than a prescription\.

**Implement least privilege access**  
When you attach the [IAM](#microservice-extractor-security-iam) policies as inline policies to your IAM user, grant only the permissions that are required to perform the specified task\. Implementing least privilege access is fundamental in reducing security risk and the impact that could result from errors or malicious intent\.