# cocos_creator_mvvm_tools 0.1.1

### Release notes
v0.1.0-The stable version of Typescript
v0.1.1-Fix the error of VMParent onLoad sequence and adjust the time of initial value of some components

### Version plan
Ported Cocos Creator 3D 1.2 version, enhanced functions
Port Cocos Creator 3.0 version (to be confirmed)

### Introduction

The mvvm tool set for cocos creator, get rid of the traditional MVC way of setting node attributes to control the UI. You can handle UI performance more quickly and in detail. Do not write a line of code to complete the complex display logic. The purpose of designing this framework is to solve the troublesome relationship between data and node state change and switching.

### renew
Add JS to call TS use case 2019/6/1

### Function

1. You don't need to write any code, just set the parameters of the script component and you can get immediate feedback on the value of the monitoring path.
2. More flexible access to events when data changes, and realize various detailed interactions that are difficult to handle.
3. Completely separate UI processing and game logic processing, and focus on processing business logic.

### Precautions

1. Difficulty in troubleshooting: Once the component is bound, it will become more difficult to find and investigate the location of the bug based on the situation. (Also the disadvantage of componentization)
2. After designing the data model, you cannot change the attribute name at will. Once you need to modify it, you must open Cocos to change it, which will depend on the editor operation. Therefore, a small component is provided internally to replace path names in batches.

### Project structure

The core script files are stored in the assets\Script\modelView path, all must be imported to use

-**JsonOb.ts**-Realize the basic observer mode, the callback function will be called automatically when the bound data is changed. You can replace it with an observer written by yourself at any time.
-**ViewModel.ts**-The core module of the VM, dynamically manages the ViewModel, and uses cc.director.emit to notify the node components in the game to change state.
-**VMBase.ts**-VM monitoring core component, used to receive the value change message of the ViewModel. Derivative components such as VMCustom /VMEvent are inherited from VMBase
-**VMParent.ts**-VM parent component, suitable for prefab pop-up windows. It binds data to components that inherit VMparent, which only belongs to the instance created this time. It needs to be inherited and used in a special way.

### Instructions

-Basic usage

  **Import Framework**-Import all scripts in assets\Script\modelView
  **Create data model**-Create a new data script anywhere, define your own data model, and use VM.add(data,'tag') to add viewModel. The data can be referenced through the VM, or the data model can be managed globally by yourself.
  **Hanging script**-Add the component VMCustom directly to the editor, it will automatically identify the component and its properties that need to be set, such as cc.Label, cc.Progress, etc. As long as you fill in the corresponding watchPath, it will be automatically assigned to the properties of the component. For example, fill in global.play.hp
  **Change data**-Change the value of global.play.hp arbitrarily in the game, and the corresponding label will automatically change the value.

-Global registration of VM: (Global free use path)
   VM.add(data,'tag'); //

-Partial components use VM: (relative path only used within components)
  1. Inherit the VMParent component
  2. Set data in the component (data attribute)
  3. Relative path Use *.name to set watchPath, VMParent will automatically replace * with the actual ViewModel tag during onLoad to monitor data changes.

### Help description

Please check the attached document for specific usage: /docs
[Use Document] (https://github.com/QuiLeVan/cocos_creator_mvvm_tools/tree/master/docs)
