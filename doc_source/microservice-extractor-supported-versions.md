# Supported use cases<a name="microservice-extractor-supported-versions"></a>

AWS Microservice Extractor for \.NET supports the following use cases\.

**\.NET Framework**  
AWS Microservice Extractor for \.NET supports \.NET Framework ASP\.NET web service applications hosted on IIS\. Specifically, Microservice Extractor supports the following CLR 4\.0 versions:
+ **Application visualization**: \.NET Framework version 4\.0 and later
+ **Application extraction**:
  + \.NET Framework version 4\.8\.0
  + \.NET Framework version 4\.7\.2
  + \.NET Framework version 4\.7\.1
  + \.NET Framework version 4\.7\.0

Microservice Extractor analyzes `C#` source code\. Microservice Extractor does not support ASP\.NET Web Pages or Razor Pages\.

**Extraction**  
Microservice Extractor supports extraction for the following use cases:
+ Classes are extracted in their entirety\. Partial class extraction is not supported\.
+ Classes do not change during compilation\. Classes that change class structure during compilation are not supported\.

**Controllers**  
Microservice Extractor supports the following actions in relation to controllers:
+ For applications with controllers, Microservice Extractor converts local method calls at the controller level to network calls to the extracted service\.
+ For other applications, Microservice Extractor adds code comments by default\. If you choose the advanced option for **Method invocations from the application to the extracted service** during extraction, Microservice Extractor replaces local method calls with network calls, where possible\.
+ For MVC applications, Microservice Extractor copies the views \(\.cshtml file\) to the extracted service to be able to render the relevant HTML when returning the response\.