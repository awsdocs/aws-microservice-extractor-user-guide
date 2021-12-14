# Onboard an application<a name="microservice-extractor-use-onboard"></a>

To onboard your application, perform the following steps\.

1. Navigate to the **Applications** page of the Microservice Extractor tool by either choosing it from the left navigation pane of the application, or by choosing **Next** from the **Setup AWS Microservice Extractor for \.NET** page\. In the **Applications** component, choose **Onboard application**\. The **Onboard application** option is disabled if you have not selected an AWS named profile from the **Set up Microservice Extractor** page\.

1. On the **Onboard application** page, enter the following information for the application you want to onboard\.
   + **Application details**\. Enter a **Name** and optional **Description** for your application\.
   + **Source code**\. Provide the ASP\.NET **solution file** \(for example, the \.sln file\)\. Choose the application project file to upload to Microservice Extractor\. The file must be buildable and use ASP\.NET\. The source code and its dependencies must be local to the on\-premises machine or Amazon EC2 instance on which Microservice Extractor is run\.
**Note**  
Microservice Extractor uses [MSBuild](https://docs.microsoft.com/en-us/visualstudio/msbuild/msbuild) to build your application\. If your application uses custom build scripts, you will encounter an error during the application analysis\.
   + **Runtime profiling data — optional**\. Upload the outputted `.csv` file from the runtime profiling performed for your application\. For steps to run the profiler, see the [Runtime profiling prerequisites](microservice-extractor-install.md#microservice-extractor-install-runtime-profiling)\. You can find the outputted `.csv` file in the output directory configured for the `SERVICEEXTRACT_PROFILER_OUTPUT_DIR` environment variable\. 
**Note**  
You can't change the source code or runtime profiling data that was input after onboarding\. If you want to make changes to these input files, you must onboard the application as a new application\.
   + **Analyze \.NET Core portability — optional**\. If Porting Assistant for \.NET is installed on your local machine, you can choose to include \.NET Core compatibility data in the visualization of your application\.

1. Choose **Onboard Application**\. Microservice Extractor analyzes your source code and uses the analysis and runtime metrics to produce a graphical representation of your application\. 

1. When the analysis completes, the application will show a build status of **Success** on the **Applications** page\. From here, you can select the application and choose **Launch visualization**, or choose **View dependency graph** in the build success banner\. The graph shows node dependencies, runtime metrics, such as runtime call counts, and static references between code artifacts, such as classes\. If you choose the application name, you are taken to the **Application details** page, where you can view and edit the details you entered when you onboarded the application\.

   If the application shows a **build failed** status, review the error message, and choose **Update source code** to remediate\.
**Note**  
We recommend that you wait until the build status shows **Success** before you navigate to the **View details** page\.