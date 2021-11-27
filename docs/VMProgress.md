## VM Progress

### introduce 

VM component Progress bar settings, suitable for any progress bar components, such as ProgressBar, cc.Slider, etc. Accept two watchPath values, and finally reflect the change result on the progress property. The usage is the same as the VM Custom component.

### Editor properties

-`Controller`-Activate the controller to enable two-way binding, otherwise you can only receive messages
-`Watch Path Arr`-Bind the numeric monitoring path array. Note that you must set an array with a length of 2. The first value is the minimum value, and the second value is the maximum value, so that the progres property can be calculated correctly
-`Component Name`-the name of the bound component (it will be automatically identified according to the script configuration)
-`Component Property`-bind the property that needs to be monitored on the component (it will be automatically identified according to the script configuration)
-`refreshRate`-refresh interval frequency (only affects the frequency of dirty checking), it takes effect after the controller is turned on
