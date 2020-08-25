## Enhanced NavMesh Agent

This MonoBehaviour is a direct replacement for the Unity [NavMeshAgent](https://docs.unity3d.com/ScriptReference/AI.NavMeshAgent.html) MonoBehaviour. It implements the same properties and methods but internally is a Crowds agent. This provides an easy path to migrate from traditional a traditional NavMeshAgent based system to the higher quality Crowds system.

### Migration

To migrate a GameObject from a `NavMeshAgent` to an `EnhancedNavMeshAgent` simply add the `Enhanced Nav Mesh Agent` script to the GameObject. This will automatically create several other MonoBehaviours (`Synchroniser`, `Entity Identity`, `Convert To Entity`, `Navigator`, `Steer For Goal`), these are the Crowds behaviours which the `EnhancednavMeshAgent` will automatically configure.

Once the `EnhancedNavMeshAgent` MonoBehaviour has been added click `Import From Nav Mesh Agent` to automatically copy all of the settings from the `Nav Mesh Agent` MonoBehaviour. This will disable the `Nav Mesh Agent` MonoBehaviour once it is complete.

Finally click `Auto Configure Crowds` to automatically configure some default settings on the Crowds MonoBehaviours.

## Inspector

![SteerForWander Inspector](../../../../images/EnhancedNavMeshAgentInspector.png)

#### Import From Nav mesh Agent

Automatically copies settings from a Unity `NavMeshAgent` MonoBehaviour to this `EnhancedNavmeshAgent` and disables the `NavMeshAgent`.

#### Auto Configure Crowds

Automatically configures Crowds components to act in a similar way to the Unity `NavMeshAgent`.

#### Speed

Sets the maximum speed of this Agent. Equivalent to Crowds [`Navigator.MaximumSpeed`](../Navigator.md/#maximum-speed) property.

#### Angular Speed

todo

#### Acceleration

todo

#### Stopping Distance

todo

#### Auto Braking

todo

#### Radius

todo

#### Height

todo

#### Quality

todo

#### Priority

todo

#### Auto Traverse Off Mesh Link

todo

#### Auto Repath

todo

#### Area Mask

todo

## Scripting

todo