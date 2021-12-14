# Primary features<a name="drift-features"></a>

The primary features of AWS Microservice Extractor for \.NET are: 

**Application analysis and graphical representation of application classes**  
Microservice Extractor analyzes your monolithic applications and, based on the analysis, produces a graphical representation that displays the application classes, optionally configured metrics for applicable classes, and dependencies between them\. The interactive graph groups classes by functionality to help you make decisions about which parts of the application to extract as independent services\. 

**Automated packaging of grouped functionalities into smaller services**  
You can designate the parts of an application to extract as separate services by grouping parts of the application code to be removed based on the functionality they implement\. Microservice Extractor attempts to convert the grouped classes into code solutions\. Internal application method calls can be converted to API operations so that the new, smaller services can function independently from the monolithic application\.

**Porting Assistant for \.NET integration**  
You can determine whether your application dependencies are compatible with \.NET Core, and group \.NET Core compatible dependencies together using Porting Assistant for \.NET integration with Microservice Extractor\. Microservice Extractor detects whether Porting Assistant for \.NET is installed on your machine and gives you the option to include \.NET Core compatibility data\. When this option is enabled, you can view \.NET Core compatible dependencies in the visualization side panel of your monolithic application\.