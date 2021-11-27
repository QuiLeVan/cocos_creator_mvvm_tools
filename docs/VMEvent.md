## VM Event

### introduce 

VM component event, monitor the change of watchPath path value, call the callback function. You can monitor the value of multiple paths at the same time. Suitable for occasions where you need to deal with the behavior of changing values ​​by yourself. For example, if you get 1 gold coin and want to make the number flash, with VMEvent, you don't have to manually make the number flash. You can set callbacks directly in the editor to trigger the functions of other components.

### Editor properties

-`Template Mode`-Multi-path template mode, you can monitor multi-path after opening
-`Watch Path`-Bind the value monitoring path

-`Watch PathArr`-Array of paths for binding value monitoring (appears after multipath template mode is turned on)

-`Component Name`-the name of the bound component (it will be automatically identified according to the script configuration)

-`Component Property`-bind the property that needs to be monitored on the component (it will be automatically identified according to the script configuration)

-`Trigger Once`-The event notification is delivered only once, and then the component is automatically disabled

-`Filter Mode`-Filter notification events according to conditions, for example, when the value is >=30, the notification event will be notified to call Change Events

-`Change Events`-Value path change event, similar to button callback event, bind the corresponding node function to be executed in the editor
