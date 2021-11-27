## VM Modify

### introduce 

The VM component modifies the data and modifies the data of the specified path watchPath. Generally used with the cc.Button component, you can directly modify the value of the specified path after clicking the button.

### Editor properties

-`Watch Path`-Bind the value monitoring path
-`Value Clamp`-Whether to limit the modification range of the number
-`Value Min`-limit the minimum value not less than
-`Value Min`-limit the maximum value not higher than

### How to use

The setting similar to Click Events calls the method of the component on the node, to call the corresponding function on the VMModify component, you can modify the value of the path monitored by the watch Path.

-`vAddInt`-add integer
-`vSubInt`-Decrease integer
-`vMulInt`-multiply by integer
-`vDivInt`-divide by integer
-`vAdd`-add floating point number
-`vSub`-Reduce floating point numbers
-`vMul`-Multiply floating point numbers
-`vDiv`-divide by floating point
-`vString`-set string
-`vNumberInt`-set integer
-`vNumber`-Set floating point number
