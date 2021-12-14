# Extract parts of an application as independent services<a name="microservice-extractor-use-extract"></a>

Review the arrangement of the group or groups you selected and their individual nodes and dependencies on the main view of the **Visualization \(nodes and dependencies\)** page\. When you are satisfied with your groups, choose **Extract group as service** and perform the following steps:

1. On the **Review details and initiate extraction** page, review and verify the **Service details** and the **Extraction details**\. Address all of the issues listed for the nodes and dependencies\. To view the description of an issue, select the **Shared state access detected** or **Requires attention** alert under **Comments**\. Select the corresponding **Class ID** to view and address the issue in the source code\. 

   If a class accesses a state that is shared by classes that belong to multiple groups in the application, modification of the shared state may result in errors when you extract the nodes as a smaller service\. If the **Shared state access detected** message appears next to a class, check whether the class accesses a state that is shared by classes that belong to other groups\. If so, update your application source code to remove access to the shared state\. Analyze the application again before proceeding with the extraction\. 

   The following shared state accesses are detected:
   + `TempData` property in [https://docs.microsoft.com/en-us/dotnet/api/system.web.mvc.controllerbase.tempdata?view=aspnet-mvc-5.2#System_Web_Mvc_ControllerBase_TempData](https://docs.microsoft.com/en-us/dotnet/api/system.web.mvc.controllerbase.tempdata?view=aspnet-mvc-5.2#System_Web_Mvc_ControllerBase_TempData) class\.
   + `Session` property in [https://docs.microsoft.com/en-us/dotnet/api/system.web.mvc.controller?view=aspnet-mvc-5.2](https://docs.microsoft.com/en-us/dotnet/api/system.web.mvc.controller?view=aspnet-mvc-5.2) class\.

1. Select an option under **Method invocations from application to extracted service**\. Consider the following limitations for each method:
   + **Use remote method invocations** — network calls can add additional overhead to user requests\. Manual verification and refactoring may be required to ensure accuracy\.
   + **Use local method invocations** — code duplication from manual refactoring can introduce conflicting states in the application\.

1. When you are satisfied with the extraction details, choose **Extract**\. The progress of the extraction is displayed at the top of the page \. To cancel the extraction, in the extraction progress banner, select **Cancel extraction**\. If you cancel the extraction, the extraction configuration is deleted, and you must restart the extraction\.

   A successful extraction will display the output location of the extraction in the green status banner\. To view the extraction details, choose **View details** on the status banner\.

   If the extraction fails, the red status banner displays an error message\. Navigate to the **Visualization** page to verify and address issues with the unsupported classes and try again\.

**View and edit extraction details**  
You can view the details of the extraction from the **Application details** page by selecting the radio button next to the **Service name** under **Extractions**, and choosing **View details** from the **Actions** dropdown\. On the service details page, you can view the **Extraction details** and **Nodes and dependencies**\. To edit the extraction details, choose **Re\-extract service** from the **Actions** dropdown\. You must re\-extract a service in order to edit its configuration\.