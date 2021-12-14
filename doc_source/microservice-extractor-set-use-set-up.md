# Set up AWS Microservice Extractor for \.NET<a name="microservice-extractor-set-use-set-up"></a>

Perform the following steps to set up AWS Microservice Extractor for \.NET\.

1. Verify that you have completed the [prerequisite steps](microservice-extractor-prerequisites.md) to use Microservice Extractor\. 

1. From the Microservice Extractor landing page, choose **Get started**\.

1. From the **Setup Microservice Extractor** page, select an AWS named profile from the dropdown list, or **Add a named profile**\. Microservice Extractor uses your AWS named profile to share your Microservice Extractor usage data with AWS to make the Microservice Extractor tool better\. For more information about named profiles, see [Named profiles](https://docs.aws.amazon.com/cli-configure-profiles.html) in the *AWS CLI User Guide*\.

1. Add or update the **Working directory** used to store the output from the application analysis and extraction of your application\. You cannot change this directory after the application is set up\.

1. Update the **MSBuild path** to build the application\. If the path is not updated, the listed **Default path** will be used\.

1. **Microservice Extractor usage data sharing** is enabled by default\. To view the types of data collected, see [Information collected](microservice-extractor-information-collected.md)\. Clear the check box selection to disable usage data sharing\. 

1. Choose **Next** to onboard your application\.