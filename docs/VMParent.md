## VM Parent

### introduce 

If you want your component to have the ability to dynamically monitor data, you need to inherit the use of VMParent. The monitored data type is owned by the component instance itself, and is local data rather than global data.

### Attributes

`data`-Define the data type to be bound, which is only valid in this component. After definition, these data will be automatically bound.

`onBind()`-call this method after data binding is complete

`onUnBind()`-This method is called before the data binding is released

`tag`-The bound tag, the current vm instance can be obtained through this tag

`VM`-VM management object, you can use the object to get the value path

### Precautions

-If you are not clear about the inheritance mechanism, do not overwrite the onLoad() event at will. Please use the onBind() function instead of the onLoad() function, and the onUnBind() function instead of the onDestroy() function. If you are familiar with it, you can use super.onLoad() to call the parent method
-Don't use VMParent too much nesting, it may affect performance a little when binding
