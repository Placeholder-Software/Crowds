## How To Traverse Off-Mesh Links

[Off Mesh Links](https://docs.unity3d.com/Manual/class-OffMeshLink.html) are a feature of the Unity navmesh system, and off mesh link represents a connection that can be traversed but not by walking. For example, jumping over a gap or climbing up a ladder.

The [SteerForGoal](/Reference/MonoBehaviours/SteerForGoal) behaviour controls the movement of an agent along a path, including off-mesh links.

### Auto Complete

To automatically complete off-mesh links when the agent gets to them (by teleporting to the end) enable `Auto Complete Off Mesh Links` in the inspector or set `AutocompleteOffMeshLinks = true` in a script.

### Script Completion

Instead of teleporting across an off-mesh link an animation or gameplay event will usually need to be triggered.

To check if the agent is approaching an off-mesh link check the `IsApproachingOffMeshLink` property every frame. When an agent is approaching a link (i.e. there are no more turns in the path between the agent and the start of the link) it will begin using [SteerForArrival](/Reference/MonoBehaviours/SteerForArrival) behaviour to slow down and stop at the start of the link. When approaching an off-mesh link use the `DistanceToOffMeshLink` property to detect how far away from the start of the link the agent is.

Once an agent has arrived a the link it will not move until the link is completed, check the `IsWaitingAtOffMeshLink` property to detect this state. In this state you can move the agent however you like (e.g. trigger an animation).

One the agent has finished traversing the link (e.g. the animation has finished) call the `CompleteOffMeshLink` method. This accepts 2 parameters: `teleport` and `checkOffPath`. The `teleport` parameter specifies what kind of action the agent should take - set it to `true` to teleport to the end of the link, set it to `false` to plan a new path to the destination from where the agent is standing. The `checkOffPath` parameter specifies when the action (teleport/repath) should be taken - set to `true` to only take action if the agent is not on the path which was already planned, set to `false` to always take the specified action.

For example if an animation is played to move across the link call `CompleteOffMeshLink(false, true)` when the animation is completed to cause the agent to continue pathing to the destination, (planning a new path only if necessary).