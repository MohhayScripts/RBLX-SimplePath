![Version: 1.0](https://img.shields.io/badge/Version-1.0-blue?style=for-the-badge)

# SimplePath - Pathfinding Module

The SimplePath module gives you the ability to create a pathfinding script quickly with just a few lines of code; pathfinding is done using the methods from  [PathfindingService](https://developer.roblox.com/en-us/api-reference/class/PathfindingService).
<br>

- Get the SimplePath module from [Roblox library](https://www.roblox.com/library/6744337775/SimplePath-Pathfinding-Module).
- See some [examples](https://github.com/00xima/SimplePath/blob/main/EXAMPLES.md).

<br>

## API

#### Constructor:
|*`Path`* SimplePath.new(*`Model model`*, *`[Optional] Dictionary agentParamters`*)|
|:-|
|● *Creates a new Path Object* <br> ● *`model` must by a Model Instance with a PrimaryPart* <br> ● *Click [here][agentParametersLink] to find out more about `agentParameters` (may be required for custom humanoids)*|

<br>

|Status Types|Description|
|-|-|
|SimplePath.Status.PathCompleted|The goal is reached and pathfinding has ended.|
|SimplePath.Status.PathNotFound|Pathfinding is not possible.|
|SimplePath.Status.PathBlocked|There is an obstruction.|

<br>

### Path Object:

#### Properties:
|*`boolean`* Path.Visualize `Default: false`|
|:-|
|● *Set to true to visualize waypoints*|

|*`boolean`* Path.IgnoreObstacles `Default: true`|
|:-|
|● *Set to true to automatically recalculate path when the path is blocked*|

<br>

#### Methods:
|*`boolean`* Path:Run(*`BasePart/Vector3 goal`*)|
|:-|
|● ***Returns false if pathfinding is not possible, make sure to handle it*** <br> ● *`goal` must by a BasePart or a Vector3 position*|

|*`void`* Path:Stop(*`String status`*)|
|:-|
|● *Stops moving the model (only for humanoids)* <br> ● *Triggers the [`Stopped`](https://github.com/00xima/SimplePath/blob/main/README.md#events) event with the given `status`*|

|*`void`* Path:Destroy()|
|:-|

<br>

#### Events:
|*`RBXScriptSignal`* Path.Reached(*`Model model`*)|
|:-|
|● *Fires when pathfinding is complete*|

|*`RBXScriptSignal`* Path.Blocked(*`Model model`*)|
|:-|
|● *Fires when there is an obstruction*|
|Note: does not exist for non-humanoid models.|

|*`RBXScriptSignal`* Path.Stopped(*`Model model`*, *`String status`*)|
|:-|
|● *Fires if pathfinding stopped for any reason represented by `status`*|
|Note: does not exist for non-humanoid models|

|*`RBXScriptSignal`* Path.WaypointReached(*`Model model`*, *`Vector3 previousPosition`*, *`Vector3 nextPosition`*)|
|:-|
|● *Fires when the `model` reaches the next waypoint*|
|Note: If using non-humanoid models, move the model using this event, wait any amount to prevent exhaustion, and then run Path:Run() to notify the end of movement. See [examples](https://github.com/00xima/SimplePath/blob/main/EXAMPLES.md#non-humanoid-example) for more details.|

[agentParametersLink]:https://developer.roblox.com/en-us/api-reference/function/PathfindingService/CreatePath
