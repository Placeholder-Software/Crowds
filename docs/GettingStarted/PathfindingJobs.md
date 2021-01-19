## Pathfinding Jobs

Pathfinding can be a very slow operation if the scene is complex or the path is very long. It should not be run on the main thread to avoid low frame rates. The basic Unity `NavMeshAgent` sometimes calculates paths in a job (e.g. when using `destination`) but makes it _impossible_ to calculate paths for other purposes in jobs (e.g. when using `CalculatePath`). Overcrowded solves this by calculating all paths in the Unity Job System, this spreads the work over multiple frames and all of the available CPU cores so that **pathfinding work will never cause your game to stutter**!

### Migrating From A NavMesh Agent

The pathfinding system built into Overcrowded is based on the [Unity NavMesh](https://docs.unity3d.com/Manual/nav-NavigationSystem.html) and internally uses the normal Unity pathfinding algorithm. This makes it very easy to move from a Unity `NavMeshAgent` to an Overcrowded `Navigator`. See [this guide](../HowTo/ReplaceNavMeshAgent.md) for how to migrate from a Unity `NavMeshAgent` to an overcrowded `EnhanceNavMeshAgent`.

### Using Overcrowded Navigator

Every Overcrowded agent includes a [`Navigator`](../../Reference/MonoBehaviours/Navigator) MonoBehaviour. This MonoBehaviour includes the `FindPath` methods which start a pathfinding job and return a [`PathfindingTask`](../../Reference/Other/PathfindingResult/) object which represents the job. This object can be polled to check if the job has completed.

```csharp
PathfindingTask? _task;

void StartPathfinding()
{
    Navigator navigator = GetComponent<Navigator>();

    // Start pathfinding to "destination"
    _task = navigator.FindPath(destination);
}

void Update()
{
    // Don't do anything if the task doesn't exist or has been disposed
    if (!_task.HasValue || _task.IsDisposed)
        return;

    // Check if the job has finished
    // This will take a few frames for long paths.
    if (!_task.IsComplete)
        return;

    // Extract the result of the pathfinding job.
    // If this returns null it is because the task is not yet finished!
    var result = _task.TryGetResult();
    if (!result.HasValue)
        return;

    // Extract the polygons along the path
    var polygons = result.TryGetPathPolygons();

    // Do whatever you want to do with the completed path.
    DoSomethingWithCompletedPath(polygons);

    // Once you have finished working with the
    // result you **must** dispose it.
    result.Dispose();
}
```