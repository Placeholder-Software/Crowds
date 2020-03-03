## How To Find A Path

!!! note
    To make an agent walk along a path, follow this [guide](../FollowPath) instead.

The `Navigator` behaviour has two methods ([1](/Reference/MonoBehaviours/Navigator/#pathfindingtask-findpathvector3-end), [2](/Reference/MonoBehaviours/Navigator/#pathfindingtask-findpathvector3-start-vector3-end-int-areamask-int-agenttype-nativeslice-areacosts-default)) to find a path from an agent to a destination.

### Basic FindPath

To find a path from an agent to a position, first call `FindPath`

    Navigator agent;
    Vector3 destination;
    var task = agent.FindPath(destination);

This returns a [`PathfindingTask`](/Reference/Other/PathfindingTask/) which represents the pathfinding job running on another thread. It may take several frames to finish if the path is very long or the pathfinder is very busy.

### Advanced Pathfind

There is another `FindPath` method which allows configuration of many more parameters, including the start and end position:

    Navigator agent;
    Vector3 start;
    Vector3 end;
    int areaMask;
    int agentType;
    var task = agent.FindPath(start, end, areaMask, agentType);

This method also returns a `PathfindingTask`.

### Querying A Pathfinding Task

To cancel the a PathfindingTask at any time before it is finished:

    task.Dispose();

Each frame check if the job is finished by trying to get a [`PathfindingResult`](/Reference/Other/PathfindingResult/) from it:

    var result = task.TryGetResult();
    if (result.HasValue)
    {
        // Pathfinding Is Finished
    }

The result may represent a pathfind which completed with a failure, for example if there is no path to the destination. This can be checked with the `IsFailure` property:

    if (result.IsFailure)
    {
        // Pathfind Failed
    }
    else
    {
        // Pathfind Success
    }

The result can be used to retrieve the polygons in the path:

    var polys = result.Value.TryGetPathPolygons();

Or the portals in the path:

    var portals = result.Value.TryGetPathPortals();

Both `polys` and `portals` will be null if the pathfind was a failure.