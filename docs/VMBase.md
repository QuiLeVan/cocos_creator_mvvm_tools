## VM Base

### introduce 

VM basic components only implement data binding and need to be inherited and used. You can implement your own VM components by inheriting VM Base. Of course, it is sufficient to use other component scripts provided by this tool under normal circumstances.

### Script attributes

-`watchPath`-The path that needs to be monitored, how you define the structure in the VM, just write the value path here.

   For example, the viewModel of the global tag should take the value player.atk, which is gloabl.player.atk.

-`watchPathArr`-The multipath array that needs to be monitored, the same as above, but it is an array of paths that needs to be monitored.

-`templateMode`-template mode (multi-path mode), all paths in the watchPathArr array can be monitored after being enabled

-`templateValueArr`-Cache the value of the monitoring path. When the value of a monitoring path changes, the value cached in the array will be automatically updated. Generally do not need to consider the use.

-`VM`-Reference of VMManager object, refer to the description of ViewModel

-`onLoad()`-Split in advance and analyze the listening path to catch some errors

   **If you need to override the onLoad method**, please call **super.onLoad()** in order to execute the default method. Overwriting directly will result in the loss of the functionality of the function.

-`onEnable()`-When the node is activated, the initial value of the object is updated, and the monitoring of watchPath is turned on at the same time.

  **Rewriteable**, you need to call super.onEnable() to handle the parent method when rewriting

-`onDisable()`- When closing the node, turn off the monitoring of watchPath.

  **Rewriteable**, you need to call super.onDisable() to handle the parent method when rewriting

-`onValueInit()`- Call the function when initializing the value

  Virtual methods can be overridden directly.

-`onValueChanged(newValue,oldValue,pathArray)`-call the function when the value changes

  Virtual methods can be overridden directly.
