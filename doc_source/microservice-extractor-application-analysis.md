# Application analysis and extraction<a name="microservice-extractor-application-analysis"></a>

AWS Microservice Extractor for \.NET analyzes the source code of a monolithic application and creates a visualization of the application, which includes nodes, dependencies, call flows, and relevant metrics\. You can use the visualization of the application to make informed decisions about the structure of the application, and to identify parts of the application to group together and extract as independent services\. 

After Microservice Extractor extracts a specified functionality group within the application, you can manually package and deploy the functionalities as independent services in containers\. You can then integrate the smaller services with your custom workflows\.

Extracting monolithic applications into smaller, independent services is an iterative process\. Based on your requirements, you can repeat the process by onboarding the newly extracted monolithic application into Microservice Extractor\. This further assists with identifying and extracting components as independent services\.