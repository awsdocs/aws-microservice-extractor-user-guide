# Information collected<a name="microservice-extractor-information-collected"></a>

Usage data sharing is enabled by default\. You can disable usage data sharing by clearing the check box for usage data sharing on the AWS Microservice Extractor for \.NET **Settings** page \. 

When usage data sharing is enabled, Microservice Extractor collects the following information when you onboard your source code:
+ Success and failure operations performed during onboarding, static code analysis, application build, and graph creation\.
+ Resources consumed during operations, such as CPU and memory usage\.
+ Number of nodes and dependencies\.
+ Number of detected islands\.

Microservice Extractor doesn’t collect proprietary information, such as source code\. In case of failure, the tool might collect stack traces to improve product experience\.

Microservice Extractor uses the information collected to continuously improve its API replacement suggestions\. Microservice Extractor periodically analyzes the collected information and updates its replacement engine so that the Microservice Extractor experience is continuously improved\.