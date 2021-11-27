## VM Custom

### introduce 

VM component customization, you can set the component name and component properties that need to be monitored, and automatically identify the component name when mounting. More general use. Suitable for any self-made components. (If you want to automatically recognize the component name you wrote, you can modify the script configuration content).

### Editor properties

-`Controller`-Activate the controller to enable two-way binding, otherwise you can only receive messages
-`Watch Path`-Bind the value monitoring path

-`Component Name`-the name of the bound component (it will be automatically identified according to the script configuration)

-`Component Property`-bind the property that needs to be monitored on the component (it will be automatically identified according to the script configuration)

-`refreshRate`-refresh interval frequency (only affects the frequency of dirty checking), it takes effect after the controller is turned on
