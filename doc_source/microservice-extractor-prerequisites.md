# Prerequisites to use AWS Microservice Extractor for \.NET<a name="microservice-extractor-prerequisites"></a>

**Topics**
+ [Prerequisites for analysis and extraction](#microservice-extractor-prerequisites-analysis-extraction)
+ [Required IAM policies](#microservice-extractor-iam)

## Prerequisites for analysis and extraction of monolithic application<a name="microservice-extractor-prerequisites-analysis-extraction"></a>

To use Microservice Extractor to analyze and extract a monolithic application to deploy into smaller services, you must have the following:
+ A valid AWS CLI profile to publish metrics\. For information about how to configure an AWS CLI profile, see [Configuring the AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html)\.
+ A monolithic application that must be a \.NET Framework ASP\.NET web service application hosted on IIS with the \.NET Framework developer pack installed\.
+ The ability to build the application solution with [MSBuild](https://docs.microsoft.com/en-us/visualstudio/msbuild/msbuild)\.
+ One of the following operating systems for analyzing the application and creating the visualization:
  + Windows 7 or later
  + Windows Server 2016 or later
+ The following build tool located in the path of the user running the application:
  + `msbuild`\. For more information, see the [MSBuild documentation](https://docs.microsoft.com/en-us/visualstudio/msbuild/msbuild?view=vs-2019)\.
+ For the application analysis, you must have:
  + \.NET Framework version 4 or later compatibility with source code solution\.
  + 10 GB minimum of free disk space, in addition to the size of your application\.
  + 8 GB minimum of available memory\.
  + Compute power equivalent to or greater than that of an Intel Core i3 3\-GHz processor\.
+ For the extraction, you must have:
  + \.NET Framework version 4\.7 or 4\.8 compatibility with source code solution\.
  + 20 GB minimum of free disk space, in addition to twice the size of your application\.

## Required AWS Identity and Access Management policies<a name="microservice-extractor-iam"></a>

To perform certain operations using AWS Microservice Extractor for \.NET, you must attach AWS Identity and Access Management \(IAM\) policies to your IAM user\. You must use permanent AWS credentials to use Microservice Extractor\. Temporary credentials, such as authentication tokens, are not supported\. This section includes the policies that you must attach to your IAM user, and also instructions for attaching IAM policies to an IAM user\.

You must use a valid AWS CLI profile to use the assessment tool and run the commands to complete an extraction\. For information about how to configure your AWS CLI profile, see [Configuring the AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html)\.

### How to attach an IAM policy to an IAM user<a name="microservice-extractor-iam-how-to-attach-policy"></a>

Perform the following steps to attach an IAM policy to an IAM user to grant permissions\.

1. Sign in to the AWS Management Console and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the left navigation pane, choose **Policies**\.

1. Choose **Create policy**\.

1. Choose the **JSON** tab and copy and paste the policy into the text box\.

1. Choose **Review Policy** and enter a **Name** and **Description** for the policy\.

1. Choose **Create Policy**\.

1. Filter the list of policies with the name of the policy that you just created\.

1. Select the radio button next to your new policy, and from the **Policy actions** dropdown, select **Attach**\.

1. Select the **User name** of the IAM user to which to attach the policy\.

1. Choose **Attach policy**\.

1. When you select an AWS profile from the dropdown in the **Set up Microservice Extractor** page of the tool, select the same IAM profile to which you attached the following permissions policies\.

### Permissions to use the AWS Microservice Extractor for \.NET assessment tool<a name="microservice-extractor-iam-assessment"></a>

To use the AWS Microservice Extractor for \.NET assessment tool, you must create an IAM policy that includes the following permissions attached to your IAM user\. To view the type of application data collected by Microservice Extractor, see [Information collected](microservice-extractor-information-collected.md)\.

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Resource": [
        "*"
      ],
      "Action": [
        "serviceextract:GetConfig"
      ]
    },
    {
      "Sid": "SectionForMetricsService",
      "Effect": "Allow",
      "Action": "execute-api:invoke",
      "Resource": [
        "arn:aws:execute-api:us-east-1:*:*/prod/POST/put-metric-data",
        "arn:aws:execute-api:us-east-1:*:*/prod/POST/put-log-data"
      ]
    }
  ]
}
```