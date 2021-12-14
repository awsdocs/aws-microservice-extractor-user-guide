# Work with the application visualization<a name="microservice-extractor-use-visualization"></a>

The **Visualization** tab displays the application nodes and dependencies in graphical format\. The initial view on the **Visualization **tab is the main view\. The circles represent nodes, and the arrows show dependencies and direction between nodes, incoming or outgoing\. If you choose **Explore alternate visualizations for grouping**, Microservice Extractor groups your application nodes according to namespaces or islands\. By default, no groups are created\. The main view reflects any updates you make to your groupings using the alternate visualization\. 

**Topics**
+ [Visualization features](#microservice-extractor-use-visualization-features)
+ [Main visualization](#microservice-extractor-use-visualization-main)
+ [Alternate visualization](#microservice-extractor-use-visualization-alternate)

## Features of the AWS Microservice Extractor for \.NET visualization tool<a name="microservice-extractor-use-visualization-features"></a>

You can perform the following tasks from the **Visualization \(nodes and dependencies\)** page to help you group your application nodes to extract as a smaller service\. 
+ **Create custom groups to visualize a segmentation of the service**

  You can create groups in the following ways:
  + **Drag and drop \(main view only\)** — Select one or more nodes by clicking on them, then drag the node or nodes together\.
  + **Choose or right\-click \(main and alternate views\)** — Choose or right\-click a node to open the **Actions** menu\. From the **Actions** menu, you can choose to **Add node to group**\. The **Add node\(s\) to group** pane appears on the right, where you can choose to add nodes to an existing group or create a new group, and select the **Group name** and, optionally, the **Group color** \. 

  Groups are indicated by dotted rectangles\. You can collapse and expand groups by choosing the minimize and maximize icons in the left corner of each rectangle\. Collapsing a rectangle helps to reduce visual noise as you focus on other areas of the service\.
+ **View node details**

  Select one or more nodes\. Selected nodes are indicated by a dotted circle\. Incoming and outgoing dependencies for the selected nodes are highlighted as red \(outgoing\) or blue \(incoming\)\. If you select more than one node, each selected node will appear as dotted, and the dependencies will be highlighted for all of the selected nodes\. When you choose or right\-click on a node, you can select **View node details** from the **Actions** menu\. The **Node details** panel appears on the right\. **Node details** include the following tabs and information for one or more selected nodes:
  + **General** — Shows the selected nodes, their dependencies, and runtime profiling information\. The arrows, or **Edges** show the direction of the dependency, incoming or outgoing\. The call count for each node dependency is also displayed\. 
  + **\.NET Core portability** — Shows the selected nodes and their \.NET Core portability status\. If a node is not compatible for \.NET Core portability, hover over the status message to view the details and potential remediation\. 
+ **Reset view**

  Choose **Reset view** to reset the visualization to the original state, or as it was arranged when you first launched it\. All new groups are removed, and all changes will be discarded\.
+  **Add nodes to a namespace group** \(**Alternate visualization for grouping your application**\)

  From the **Alternate visualization for grouping your application** view, under the **Namespace view** tab, choose a node or namespace, and choose or right\-click on it to add it to a namespace group\. From the **Actions** menu, choose **Add node to group** and add the details about the group to which the node should be added in the **Add node\(s\) to group **pane on the right\. When you return to the main view, your updates in the namespace view will be reflected\. Note that you cannot drag and drop nodes in the **Namespace view**\. 
+ **View namespace details** \(**Alternate visualization for grouping your application**\)

  From the **Alternate visualization for grouping your application** view, under the **Namespace view** tab, choose a node or namespace, and choose or right\-click it to view namespace details\. From the **Actions** menu, choose **View namespace details**\. The **Namespace details** pane appears on the right, which displays the following information:
  + **General** — Displays the selected nodes, their dependencies, and information about possible shared state access\.
  + **Node summary** — Displays the edges between nodes\.

  When you return to the main view, any updates you made in the namespace view will be reflected\.
+ **View islands, and add nodes to an island**

  The **Island view** displays the nodes arranged as independent islands of connected nodes\. No dependencies are detected to or from nodes within an island and nodes within other islands\. The **Island view** helps you to identify potential node groupings to extract as independent services\. 

  When you return to the main view, any updates you made in the **Island view** will be reflected\. You cannot drag and drop nodes in the **Island view**\. 
+ **View ****Legend**

  The **Legend** displays the meanings of the symbols in the visualization\. 
  + A gray shaded circle indicates a node\.
  + A dotted circle indicates a selected node\.
  + A gray rectangle indicates a group\.
  + A gray rectangle that contains an expand icon indicates a collapsed group\.
  + A blue arrow indicates a dependency incoming to a node\.
  + A red arrow indicates a dependency outgoing from a node\.
+ **View ****Group classification**

  Choose **Group classification** from the bottom of the visualization to view the name, ID, and color assigned to each group in the visualization\.
+ **View runtime profiling information**

  You can view the number of call counts from the main view by hovering over the arrows in the visualization\. From the **Alternate visualization for grouping your application** view, you can hover over the rectangle edges to view the number of nodes, and incoming and outgoing dependencies\. 
+ **Search and filter**

  From the main visualization page, you can search and filter by **Class ID** or **Group name** by selecting either option from the dropdown list of the search bar, and then entering the **Class ID** or **Group name** in the search bar\. You can clear your filters by selecting **Clear filters**\.
+ **Edit group name and color**

  After you have created a group, you can edit the name and color of the group by choosing or right\-clicking it to open the **Actions** menu, then choosing **Edit group name and color**\. You can update the group name and color in the **Edit group name and color** pane that appears on the right\. 

## Main visualization<a name="microservice-extractor-use-visualization-main"></a>

After you onboard an application, Microservice Extractor displays its nodes and dependencies as a graph\. No groups are created by default\. You can create groups, modify them, or create new groups to associate with a functionality that guides refactoring\. Use the main visualization to view your groups and prepare for extraction after creating groups in the main visualization, or after exploring recommended groupings based on namespace and islands using the alternate visualization\.

Manually remove node dependencies to prepare parts of your application for extraction as smaller services\. The parts are displayed as groups in the graph\. Microservice Extractor can also extract API endpoints as separate services by isolating the code that underlies the API endpoints and replacing local calls with network calls\. This creates a new implementation of the calling class in a new solution, while preserving the interface and original solution\. You can then develop, build, and deploy the new repositories independently as services\.

For more information about actions you can take from the main visualization, see [Features of the AWS Microservice Extractor for \.NET visualization tool](#microservice-extractor-use-visualization-features)\.

For help with grouping your application by namespace or islands, use the [alternate visualization](#microservice-extractor-use-visualization-alternate)\.

## Alternate visualization<a name="microservice-extractor-use-visualization-alternate"></a>

You can explore suggested groupings for your nodes by choosing **Explore alternate visualizations for grouping** from the main visualization\. The **Alternate visualization for grouping your application** page displays tabs for **Namespace view** and **Island view**\.

**Namespace view**  
The **Namespace view** displays nodes grouped by namespace\. Namespace groups are represented by dotted rectangles\. You can add and remove nodes from a group by choosing or right\-clicking a node, which displays a menu of options\. This menu includes options to **Add node to group** and **Remove node from group**\. When you select one of these options, you can customize the nodes to add or remove using the right\-hand pane\. 

If you are working with a large application and want to collapse a namespace group, choose the minimize symbol in the upper left corner of the rectangle\. Choose the expand symbol to reopen it\.

To add all nodes from a single namespace to a group, right\-click on a namespace and choose **Add all nodes to group**\.

To view details about a namespace, choose or right\-click a group or node, and choose **View namespace details**\. The details will appear in the **Namespace details** pane on the right\. If a class accesses a state that is shared by classes that belong to multiple groups in the application, modification of the shared state may result in errors when you extract the nodes as a smaller service\. If the **Shared state access detected** message appears next to a class, check whether the class accesses a state that is shared by classes that belong to other groups\. If so, update your application source code to remove access to the shared state\.

You can view runtime profiling information \(call count and dependency direction\) by hovering over the edges of a group\. 

Return to the main view at any time by choosing **Back to main view**\. When you return to the main view, any updates you made in the namespace view will be reflected\.

**Island view**  
The **Island view** displays the nodes arranged as independent islands of connected nodes\. No dependencies are detected to or from nodes within an island and nodes within other islands\. The **Island view** helps you to identify potential node groupings to extract as independent services\. 

You can return to the main view at any time by choosing **Back to main view**\. When you return to the main view, any updates you made in the **Island view** will be reflected\.

For more information about actions you can take from the alternate visualization, see [Features of the AWS Microservice Extractor for \.NET visualization tool](#microservice-extractor-use-visualization-features)\.