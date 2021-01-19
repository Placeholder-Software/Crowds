Overcrowded includes a pathfinding system based on the built in Unity pathfinding system. The Overcrowded pathfinder performs all pathfinding work in a Job (multithreaded) and rate limits the amount of work done in each pathfinding job per frame so that pathfinding can never negatively impact frame rates.

In most cases you do **not** need to interact directly with the Overcrowded pathfinding system. If you want an agent to follow a path you should use the [`GoalPosition`](../HowTo/FollowPath.md) of the agent. If you just want to find a path between two locations you can simply use the Unity [pathfinding APIs](https://docs.unity3d.com/Manual/nav-Overview.html).

## Creating A Pathfinding Job

Pathfinding jobs are represented as entities with a `PathfindingQuery` component and an optional `PathfindingQueryCost` buffer:

```csharp
// Create a `NavMeshQuery` to find start/end points
using (var q = new NavMeshQuery(NavMeshWorld.GetDefaultWorld(), Allocator.Persistent))
{
    // Convert start/end positions into navmesh locations
    var start = q.MapLocation(start_position, size, agentType, areaMask); 
    var end = q.MapLocation(end_position, size, agentType, areaMask); 

    // Create a new entity
    var entity = EntityManager.CreateEntity();

    // Attach a query component
    EntityManager.AddComponentData(entity, new PathfindingQuery(NavMeshWorld.GetDefaultWorld(), start, end, areaMask));

    // If you want to set area costs, do this:    
    var buffer = EntityManager.AddBuffer<PathfindingQueryCost>(entity);
    for (var i = 0; i < 32; i++)
        buffer.Add(cost_of_area(i));
}
```

This will be scheduled in the pathfinding system and updated each frame. Each frame you can check for completion:

```csharp
var completed = EntityManager.HasComponent<PathfindingComplete>(entity);
```

Once the job is complete the `PathfindingComplete` component contains data about the completed job. The `Status` field indicates if the job was completed successsfully, partial, or was a failure.

```csharp
var complete = EntityManager.GetComponentData<PathfindingComplete>(entity);
Debug.Log(complete.Status);
```

If the job was completed successfully or partially the path geometry will be stored in two buffers.

The portals buffer contains a list of lines which the agent must pass through in order to complete the path:

```csharp
var portals = EntityManager.GetBuffer<PathfindingResultPortal>(entity);
```

The polygons buffer contains a list of polygon IDs which makes up the path:

```csharp
var polygons = _manager.GetBuffer<PathfindingResultPolygon>(entity)
```