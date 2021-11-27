## VM State

### introduce 

VM component status conditions, according to the watchPath path, determine whether the value meets the conditions, and then set the status of the corresponding node. The color of the node, the activation and deactivation of the node, etc. can be changed according to the data.

### Editor properties

-`Watch Path`-Bind the value monitoring path
-`Foreach Child Mode`-a special way of comparing values, it will compare the names of all child nodes under the current node as the value comparison to control the display status of all child nodes.
-`Foreach Child Type`-`NODE_INDEX` compare node index value or `NODE_NAME` compare node name
-`Condition`-Judgment condition, whether the size of the judgment value meets the condition
-`Value Action`- effect behavior, the condition to be executed when the state is satisfied
-`Watch Nodes`-Nodes that need to change state, if not set, all states of this node and its child nodes will be changed by default.

### Effect behavior

-`NODE_ACTIVE`-Change the active state of the node (mounting to this node is invalid)

-`NODE_VISIBLE`-Change the display state of the node (opacity switch). Mounting to this node is valid and only affects the display.

-`NODE_OPACITY`-change the opacity of the node

  `Action Opacity`-Set the opacity value

-`NODE_COLOR`-change the color of the node

  `Action Color`-set the value of the color

-`COMPONENT_CUSTOM`-completely customizable change component properties

  `Component Name`-component name

  `Component Property`-Properties on the component

  `Default Value`-Default value

  `Action Value`-the value changed when the condition is met

### Precautions

The NODE_ACTIVE condition does not change the active state of its own node
