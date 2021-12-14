# Concepts<a name="microservice-extractor-concepts"></a>

The following concepts and definitions can help you to understand the AWS Microservice Extractor for \.NET tool\.

**Nodes**  
Nodes represent the classes in the source code of the monolithic application\.

**Groups**  
Closely related functions are organized as groups of nodes in the graphical representation of a monolithic application\. Application nodes are displayed with their dependencies to help you understand the functional architecture of your application\. This visualization of the application nodes and dependencies can help you to group them together by functionality\.

**Islands**  
Islands are nodes arranged as independent groups of connected nodes\. Nodes within an island do not have any detected dependencies to or from nodes within other islands\.

**Visualization**  
The Microservice Extractor visualization uses source code analysis and runtime metrics to produce a graphical representation of a monolithic application\. The graph shows dependencies between application nodes, call counts, and static references between code artifacts\. You can use the graph and call counts to understand the dependencies between nodes, and to identify heavily called ones\. You can run the assessment tool from the standalone Microservice Extractor application\.

**Extraction**  
Extraction, using Microservice Extractor, is the process of separating out logically grouped parts of a monolithic application into smaller, independent services\. These parts are referred to as islands in the visualization of an application\. You can perform an extraction using Microservice Extractor after an application has been assessed\. 