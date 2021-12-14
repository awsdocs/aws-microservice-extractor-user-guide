# Troubleshooting AWS Microservice Extractor for \.NET<a name="microservice-extractor-troubleshooting"></a>

The following remediation strategies can help you troubleshoot problems with AWS Microservice Extractor for \.NET\.

**Topics**
+ [AWS profile errors](#troubleshooting-failure-profile-checker)
+ [Build failures](#troubleshooting-build)
+ [Extraction errors](#troubleshooting-extraction)
+ [Application artifact location](#troubleshooting-logs)
+ [Onboarding and visualization errors](#troubleshooting-onboarding)
+ [Creating groups](#troubleshooting-groups)
+ [Uninstalling application](#troubleshooting-uninstalling)
+ [Metrics and logs collected by AWS Microservice Extractor for \.NET](#troubleshooting-metrics-logs)
+ [Questions and feedback](#troubleshooting-questions)

## AWS profile errors<a name="troubleshooting-failure-profile-checker"></a>

**Description**  
An error regarding the specified AWS profile is returned\. For example:

```
The specified AWS profile is invalid or does not have permission to send metrics to AWS. Please refer to the Microservice Extractor User Guide for instructions on how to setup a valid AWS profile for use with Microservice Extractor.
```

**Solution**
+ Verify that you have attached the required AWS Identity and Access Management \(IAM\) policies to your IAM user\. To view the required policies, see the [Microservice Extractor prerequisites](microservice-extractor-prerequisites.md)\.
+ Add a named AWS profile with proper credentials, if required\. For more information, see [Named profiles](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-profiles.html) in the *AWS CLI User Guide*\.

## Build failures<a name="troubleshooting-build"></a>

**Description**  
The build fails when you attempt to build your repositories\.

**Solution**  
Verify the following:
+ The application is supported by Microservice Extractor\. See [Prerequisites for analysis and extraction of monolithic application](microservice-extractor-prerequisites.md#microservice-extractor-prerequisites-analysis-extraction) to view the application prerequisites\.
+ You have installed MSBuild, and Microservice Extractor is pointing to it on the **Settings** page\.
+ MSBuild is working properly\. Check the MSBuild log on the **Application details** page\. If there is no preview, or choosing the log returns an error, then MSBuild is likely failing\. Verify that you can build the application manually to see if MSBuild is working properly\.
+ Microservice Extractor is using the same MSBuild version as your installed version of Visual Studio\. If the versions don't match, you can update the MSBuild version used by Microservice Extractor from the **Settings** page\.
+ Relevant switches are added to the \.csproj file so that the default msbuild operation can use them\. By default, Microservice Extractor appends the `RestorePackagesConfig` and `restore` switches to restore NuGet packages during build\.

## Extraction errors<a name="troubleshooting-extraction"></a>

**Description**  
When you attempt to extract segments of your code as independent services, an error is returned\.

**Solution**  
For the following error:

```
Command failed: failed to run build command on ...\MyApp.sln: failed to execute command: exec: "msbuild": executable file not found in %PATH%
```
+ Verify that you have installed MSBuild and Microservice Extractor is pointing to it on the **Settings** page\.
+ Add MSBuild to the system path environment variable\.

**Check logs**
+ The `<working Dir>` referenced in this section refers to the working directory configured on the **Settings** page\. You can determine the cause of most extraction failures by viewing `<workingDir>\logs\serviceextract-extraction.log`\. Generally, the last line in this file contains a message with the cause of the error\.
+ If the error message in the log refers to a build failure, check `<workingDir>\logs\msbuild.log` for details\. Note that the extraction builds both the new service and the modified original application\. The output of each of these builds is sent to `msbuild.log`\.
+ If the error message refers to a failure to download packages, check `<workingDir>\logs\nuget.log` for details\.

## Application artifact location<a name="troubleshooting-logs"></a>

To determine the application artifact file location, do the following:

1. Find the application ID in the **Summary** section of the **Application details** page\.

1. The directory of the corresponding application is: `C:\Users\<username>\AppData\Roaming\ServiceExtract\version-1\cache\version-<versionNumber>\<applicationId>`

## Onboarding and visualization errors<a name="troubleshooting-onboarding"></a>

If you are encountering problems onboarding an application and viewing the visualization, try the following solutions:

1. The metric policy may not be properly configured\. Check the Electron main application log to check for the last succeeded state and high\-level errors\. If the metrics policy is not properly configured, the log file should display many error messages about metrics\.

1. Check the directory of the corresponding application ID for the following intermediate artifact files: `edges.csv` and `vertices.csv` inside of the `data-extraction-output` folder\.

## Creating groups<a name="troubleshooting-groups"></a>

If you experience problems when creating groups, perform the following steps:

1. Check in the directory for the corresponding application ID for the following intermediate artifact file: `tags.csv` inside of the `tags-data` folder\.

1. Verify that the groupings are correctly reflected in the file\.

1. Choose **Reset view** to remove all of the groups, and try again\.

## Uninstalling application<a name="troubleshooting-uninstalling"></a>

If you encounter issues when attempting to uninstall the application as a non\-admin user when using the **Apps and Features** interface in Windows, perform the following steps:

1. Open **Control Panel**>**Uninstall a program**\. Or, choose the **Windows** icon>**Run**> and enter `appwiz.cpl`\.

1. Choose **AWS Microservice Extractor for \.NET** from the list of installed applications, and select **Uninstall** to remove the application and its installation files\.

## Metrics and logs collected by AWS Microservice Extractor for \.NET<a name="troubleshooting-metrics-logs"></a>

AWS Microservice Extractor for \.NET collects the metrics and logs listed in the following locations of the server or desktop where the tool runs:
+ `C:\Users\<username>\AppData\Roaming\Drift\logs.`
+ `<workingDir>\logs`, where `workingDir` is the working directory configured on the **Settings** page\.

## Questions and feedback<a name="troubleshooting-questions"></a>

If you have questions that are not addressed in the AWS Microservice Extractor for \.NET technical documentation, contact aws\-microservice\-extractor\-support@amazon\.com\.

You can also provide feedback by choosing **Feedback** in the upper right\-hand corner of this page\.