## VM Label

### introduce 

The VM component text monitoring is used to handle the monitoring problem of Label. Monitor the change of the watchPath path value and change the label text content. Using template mode, you can also format the input string. You can monitor multiple paths to display information from multiple data sources on a label at the same time.

### Editor properties

-`Template Mode`-Multi-path template mode, you can monitor multi-path after it is turned on, and you can set text templates
-`Watch Path`-Bind the value monitoring path

-`Watch PathArr`-Array of paths for binding value monitoring (appears after multipath template mode is turned on)

-`Label Type`-Read-only property, automatically bind cc.Label or cc.RichText, you can modify the label you define in the script



### About template analysis

Use {{0}} {{1}} {{2}} to set the template content (set the label’s String default value). At runtime, the value of multipath monitoring will be dynamically obtained, and {{index}} will be replaced in the order of index in the array. You can add additional modifiers to format the information source. For example, {{0:int}} will display digital content as integers, {{0:time}} will display timestamps in time format, etc.

The following are currently supported formatted content:

-`int`-only the integer part is displayed
-`fix(n)`-display decimal places
-`kmbt`-shorten the length of the number in K M B T units
-`per`-display percentage
-`sep`-Separate numbers with thousands of semicolons
-`limit(n)`-limit text character length

### Custom template format

All text format processing is placed in the StringFormat class, and you can modify the functions in it according to your needs.
