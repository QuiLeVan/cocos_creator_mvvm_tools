# Feeling that using code to control the UI is a waste of life, so I made a new MVVM solution...

Are you haggard by the art's casual name*?

Are you anxious about how the nodes should be organized?

Are you bothered by controlling a lot of nodes?

`cc.find` is out of bounds?

Why is `getComponent` so long?

The name of `getChildByName` is wrong again?

Planning to change the game UI layout and logic again?

The node names and hierarchical structure are all messed up.

So let's use MVVM, everything is a component, once binding, life-long benefit.



****

### Project structure

The core script files are stored in the assets\Script\modelView path, all must be imported to use

-**JsonOb.ts**-Realize the basic observer mode, the callback function will be called automatically when the bound data is changed. You can replace it with an observer written by yourself at any time.
-**ViewModel.ts**-The core module of the VM, dynamically manages the ViewModel, and uses cc.director.emit to notify the node components in the game to change state.
-**VMBase.ts**-VM monitoring core component, used to receive the value change message of the ViewModel. Derivative components such as VMCustom /VMEvent are inherited from VMBase
-**VMParent.ts**-VM parent component, suitable for multi-instance prefab pop-up windows. It binds data to components that inherit VMparent, which only belongs to the instance created this time. It needs to be inherited and used in a special way.

****

### Introduction to Components


-`VMCustom` — Mount VMCustom, and then it will automatically identify the components of the current node (you can also set it yourself). Fill in your numerical path and you're done.
-`VMLabel` — hang on VMLabel, don’t worry about your value being zero, use template syntax {{0:int}} to format automatically to solve the problem of text data display
-`VMState` — Solve the problem of switching node state
-`VMProgress` — solve the problem of progress bar display
-`VMEvent`—Mount VMEventCall to trigger the event. Call other component methods when the value changes (combined with other components to get twice the result with half the effort)
-`VMParent` — Define ViewModel data used in a local scope

Define the data model: `VM.add(data,"tag")`

Has been cc.find, getChildByName, getComponent, so I have always wanted to organize a good solution. Part of it refers to Vue (OS: pretend to be a reference), and introduces MVVM in a way suitable for the componentization of Creator. You can even complete most of the complex UI logic without writing a line of code, which is very suitable for high-intensity detailed modification (os: let the planner change it yourself).
The core of this set of tools lies in the set of components provided, rather than Mvvm itself. It uses low-coupling component scripts to control the binding of numerical monitoring, which is less intrusive.

****

### Instructions

-**Import Framework**-Import all scripts in assets\Script\modelView

-**Create data model**-Create a data script anywhere, define your own data model, and use `VM.add(data,'tag')` to add viewModel. The data can be managed directly through the VM, or the data data model can be managed globally by yourself.

-**Hanging script**-Add the component VMCustom directly to the editor, it will automatically identify the component and its properties that need to be set, such as cc.Label, cc.Progress, etc. As long as you fill in the corresponding watchPath, it will be automatically assigned to the properties of the component. For example, fill in global.play.hp and it will be assigned to the bound component properties when the game is running.

-**Change data**-Change the value of global.play.hp arbitrarily in the game, and the corresponding label will automatically change the value.

-**Global registration VM**: (Global free use path) VM.add(data,'tag'); //

-**Partial components use VM**: (Relative path only used within the component)

  1. Inherit the VMParent component

  2. Set data in the component (data attribute)

  3. Relative path Use *.name to set watchPath, VMParent will automatically replace * with the actual ViewModel tag during onLoad to monitor data changes.

****

### Start the experience

[Picture Demo] Quick Start to bind data

[Two-way binding demo] Control health bar

[Picture Demo] Complex data project demo

Use documentation: https://github.com/wsssheep/cocos_creator_mvvm_tools/tree/master/docs

Github address: https://github.com/wsssheep/cocos_creator_mvvm_tools

If you find it useful, just click a star. If you have any suggestions, you can also raise Issuse, or leave a message under this post. This framework has been in use by itself, so it will always be maintained.
