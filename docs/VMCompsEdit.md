## VM Component Edit

### introduce 

VM component editing, providing some basic functions. You can search for the component content under the current node, which is convenient for querying the bound node and debugging information.

### Editor properties

-`Find List`-The name of the component to be queried

-`Action Type`-Action

     `SEARCH_COMPONENT`-Query component

     `ENABLE_COMPONENT`-activate and close the component

     `REPLACE_WATCH_PATH`-Replace component path

     `DELETE_COMPONENT`-delete all matching components

-`Trigger`-Check the box and the corresponding command will be executed immediately. Trigger names are different in different modes

-`Can Collect Nodes`-Collect the nodes and place them in Collect Nodes. It can only be used when the Action Type is SEARCH_COMPONENT

-`Target Path`-The target path to be searched, available when Action Type is REPLACE_WATCH_PATH

-`Replace Path`-Path value to be replaced, available when Action Type is REPLACE_WATCH_PATH

### Manual editor

Search t:VMBase in the hierarchical manager, you can also query the nodes of all VM components, and then you can perform manual management operations
