## View Model Script

### introduce 

Script usage of View Model

### method

VM is an instance of VMManager, used to manage all ViewModel instances. The ViewModel instance is mainly used to realize the two-way binding of the data. The cc.director.emit method is used internally to send the message of the data change. You don't need to pay attention to these details when using it.

We can manage all ViewModels by importing VM (VMManager) objects. **It is not recommended** to use ViewModel instances directly.

```typescript
//TS is introduced using import
import {VM} from'./ViewModel';

//JS can be imported using require, no difference in other usage
const {VM} = require('./ViewModel');
```

-`add`-Create and add a ViewModel object

  ``` typescript
  VM.add(data,tag);
  //data-the data object you want to bind
  //tag-the index tag of the data object, used to obtain the ViewModel object later
  ```

-`get`-get

  ```typescript
  let vm = VM.get(tag);//The result obtained is a ViewModel object
  let data = vm.$data; //Get the data object bound to vm
  vm.active = false; // Turn off the data notification function of vm
  ```

-`remove`-remove

  ```typescript
  VM.remove(tag);//Remove a ViewModel object with a specified tag
  ```
-`setValue`-set a value (global path starting with tag)

    ```typescript
    VM.setValue('global.player.name','wss');
    //Note that global is the label of ViewModel, player.name is the value path inside ViewModel
    //Using VM global management, the value must be set in this way of global path
    ```
-`addValue`-add a value (global path starting with tag)

  ```typescript
  VM.addValue('global.player.hp',10);
  ```

-`getValue`-Get a value (global path starting with tag)

  ```typescript
  VM.getValue('global.player.name',default);//default is the default value
  ```

-`setObjValue`-Set the value of an object in the form of a path
-`getObjValue`-Get the value of an object in the form of a path
-`bindPath`-bind the path that needs to be monitored
-`unbindPath`-unbind the path that needs to be monitored
-`active`-activate event notification of value change
-`inactive`-Turn off event notification of value changes

### example

```typescript
import {VM} from'./ViewModel';

//Build the data object
let data = {
    name:'user',
    gold: 12200,
    info:{
        id:0
    }
}
//Create a VM object and add it to VMManager for management, mark it as a'user' tag
VM.add(data,'user');

 //Get an instance of ViewModel through the'user' tag
let vm = VM.get('user');
vm.$data; // vm.$data === data;

 //Set new attribute value
vm.setValue('name','new Name');

//Get attributes
vm.getValue('gold');

 //Get attributes through relative path
vm.getValue('info.id');

//Once the value is modified, cc.director will be notified, and use emit to send a message
data.name ='my_name';

//After closing the activation state, cc.director will not be notified to pass information
vm.active = false;

//Remove ViewModel and release the reference to data
VM.remove('user');
data = null;
```
