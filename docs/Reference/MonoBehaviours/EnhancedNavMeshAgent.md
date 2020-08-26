## Enhanced NavMesh Agent

This MonoBehaviour is a direct replacement for the Unity [NavMeshAgent](https://docs.unity3d.com/ScriptReference/AI.NavMeshAgent.html) MonoBehaviour. It implements the same properties and methods but internally is a Crowds agent. This provides an easy path to migrate from traditional a traditional NavMeshAgent based system to the higher quality Crowds system.

## Migration

To migrate a GameObject from a `NavMeshAgent` to an `EnhancedNavMeshAgent` simply add the `Enhanced Nav Mesh Agent` script to the GameObject. This will automatically create several other MonoBehaviours (`Synchroniser`, `Entity Identity`, `Convert To Entity`, `Navigator`, `Steer For Goal`), these are the Crowds behaviours which the `EnhancednavMeshAgent` will automatically configure.

Once the `EnhancedNavMeshAgent` MonoBehaviour has been added click `Import From Nav Mesh Agent` to automatically copy all of the settings from the `Nav Mesh Agent` MonoBehaviour. This will disable the `Nav Mesh Agent` MonoBehaviour once it is complete.

Finally click `Auto Configure Crowds` to automatically configure some default settings on the Crowds MonoBehaviours.

## Differences

The `Enhanced Nav Mesh Agent` is not identical to the `Nav Mesh Agent`. The follows properties are not supported:
 - autoBraking - Crowds always uses autoBraking style behaviour.
 - currentOffMeshLinkData.activated - It is not possible for Crowds to get this information from the Unity low level pathfinding API.
 - currentOffMeshLinkData.linkType - It is not possible for Crowds to get this information from the Unity low level pathfinding API.
 - currentOffMeshLinkData.offMeshLink - It is not possible for Crowds to get this information from the Unity low level pathfinding API.
 - nextOffMeshLinkData.activated - It is not possible for Crowds to get this information from the Unity low level pathfinding API.
 - nextOffMeshLinkData.linkType - It is not possible for Crowds to get this information from the Unity low level pathfinding API.
 - nextOffMeshLinkData.offMeshLink - It is not possible for Crowds to get this information from the Unity low level pathfinding API.
 - navMeshOwner - It is not possible for Crowds to get this information from the Unity low level pathfinding API.
 - isStopped - Not Implemented. Open a feature request if you need this feature.
 - nextPosition.set - Not Implemented. Open a feature request if you need this feature.
 - velocity.set - Not Implemented. Open a feature request if you need this feature.

## Inspector

![Enhanced Nav Mesh Agent Inspector](../../../images/EnhancedNavMeshAgentInspector.png)

#### Import From Nav mesh Agent

Automatically copies settings from a Unity `NavMeshAgent` MonoBehaviour to this `EnhancedNavmeshAgent` and disables the `NavMeshAgent`.

#### Auto Configure Crowds

Automatically configures Crowds components to act in a similar way to the Unity `NavMeshAgent`.

#### Speed

Sets the maximum speed of this Agent. Equivalent to Crowds [`Navigator.MaximumSpeed`](../Navigator#maximum-speed) property.

#### Angular Speed

Sets the maximum turning speed of this Agent (degrees/second). Equivalent to Crowds [`Navigator.MaximumAngularSpeed`](../Navigator#maximum-angular-speed) property.

#### Acceleration

Get/set the maximum acceleration of this Agent. Equivalent to Crowds [`Navigator.MaximumAcceleration`](../Navigator#maximum-acceleration) property.

#### Stopping Distance

Get/set how far before the end of a path the agent should begin slowing to a stop. Equivalent to Crowds [`SteerForGoal.SlowingDistance`](../Steering/SteerForGoal#slowing-distance) property.

#### Auto Braking

Disabling this is not supported by Crowds. Always enabled.

#### Radius

Get/set the radius of this agent when avoiding collisions with other agents. Equivalent to Crowds [`Navigator.Radius`](../Navigator#radius) property.

#### Height

Get/set the height of this agent when avoiding collisions with other agents. Equivalent to Crowds [`Navigator.Height`](../Navigator#height) property.

#### Quality

Get/set the quality of local avoidance algorithm to use. Currently Crowds does not support multiple quality levels - setting this to `None` is equivalent to setting the [`Navigator.AvoidOtherAgents`](../Navigator#avoid-local-obstacles) property to false.

#### Priority

Get/set the priority of this agent compared to other agents in local avoidance, a higher priority will cause other agents to yield if they are in the way of this agent. Equivalent to Crowds [`Navigator.Priority`](../Navigator#priority-range) property.

#### Auto Traverse Off Mesh Link

Get/set if this agent should automatically teleport across off-mesh links. Equivalent to Crowds [`SteerForGoal.AutocompleteOffMeshLinks`](../Steering/SteerForGoal#autocomplete-off-mesh-links) property.

#### Auto Repath

Get/set if this agent should automatically generate a new path to the goal when the path becomes stale (e.g. the goal moves). Equivalent to Crowds [`Navigator.EnableAutoRepathing`](../Navigator#disable-automatic-repathing) property.

#### Area Mask

Get/set the area mask to use for pathfinding queries. Equivalent to Crowds [`Navigator.EnableAutoRepathing`](../Navigator#AreaMask) property.

## Scripting

todo