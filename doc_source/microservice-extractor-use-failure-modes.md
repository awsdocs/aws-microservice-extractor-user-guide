# Failure modes<a name="microservice-extractor-use-failure-modes"></a>

What used to be called a function call is now a network call\. A network call can fail for various reasons; for example, network connectivity, service outages, authentication errors, or unknown server errors\. While Microservice Extractor provides some handling for these new types of errors, you may want to update them to accommodate your error\-handling scheme\.

We recommend copying artifacts or package dependencies that lie outside the scope of the directory of your solution \(with the exception of standard “reference assemblies” installed in known locations\) into your solution directory, and adjusting project files to point to the updated location before starting automatic refactoring\.