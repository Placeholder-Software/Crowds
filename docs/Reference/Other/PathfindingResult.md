# PathfindingResult

This structure represents the result of a pathfinding job which has completed.

## Script Properties

### Status

The full status of the pathfind. See Unity [https://docs.unity3d.com/ScriptReference/Experimental.AI.PathQueryStatus.html](https://docs.unity3d.com/ScriptReference/Experimental.AI.PathQueryStatus.html).

### Start

The start location of the pathfind.

See also: [NavMeshLocation](https://docs.unity3d.com/ScriptReference/Experimental.AI.NavMeshLocation.html).

### End

The end location of the pathfind.

See also: [NavMeshLocation](https://docs.unity3d.com/ScriptReference/Experimental.AI.NavMeshLocation.html).

### IsDisposed

Indicates if this result has been disposed. No path data can be retrieved once `IsDisposed` is `true`.

### IsFailure

Indicates if the pathfind failed to compute a path to the destination.

## Script Methods

### NativeSlice<[PathfindingResultPolygon](/Reference/Other/PathfindingResultPolygon)\>? TryGetPathPolygons()

Attempts to retrieve the polygons along the path.

This returns a `NativeSlice`, which will only remain valid until this `PathfindingResult` is disposed.

### NativeSlice<[PathfindingResultPortal](/Reference/Other/PathfindingResultPortal)\>? TryGetPathPortals()

Attempts to retrieve the portals along the path. The "portals" are the edges which connect polygons along the path, the agent must pass _through_ each portal to follow the path.

This returns a `NativeSlice`, which will only remain valid until this `PathfindingResult` is disposed.

### Dispose()

Disposes this object, freeing all the memory used to store the result. This **must** be called to prevent a memory leak!