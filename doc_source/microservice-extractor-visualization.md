# Visualization<a name="microservice-extractor-visualization"></a>

AWS Microservice Extractor for \.NET creates a visualization of the monolithic application nodes, the metrics for each node, and the dependencies between them\. It provides data on the application structure required to help you decide what parts of the application you want to extract as smaller, independent services\. You can use the visualization to perform the following:
+ **Isolate dependencies ** — Use the visualization to help you isolate dependencies and automatically capture interdependencies to create groups of closely related nodes\. Nodes within each group rely on other nodes within the group\.
+ **Narrow focus ** — View all of the dependencies for a selected node, and the shared dependencies between nodes\.
+ **Assess call count ** — View the method call count number between nodes\. Call count data is provided by the runtime metrics that you upload to the tool\. 
+ **Visualize at a high level** — Get a high\-level understanding of your monolithic application, and investigate dependencies and call count metrics to make decisions about parts of the application to extract into smaller, independent services\.

![\[Visualization\]](http://docs.aws.amazon.com/microservice-extractor/latest/userguide/images/visualization.PNG)