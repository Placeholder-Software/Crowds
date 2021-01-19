## Pathfinding Jobs

Pathfinding can be a very slow operation if the scene is complex or the path is very long. It should not be run on the main thread to avoid low frame rates. The basic Unity `NavMeshAgent` sometimes calculates paths in a job (e.g. when using `destination`) but makes it _impossible_ to calculate paths for other purposes in jobs (e.g. when using `CalculatePath`). Overcrowded solves this by calculating all paths in the Unity Job System, this spreads the work over multiple frames and all of the available CPU cores so that **pathfinding work will never cause your game to stutter**!

### Migrating From A NavMesh Agent

The pathfinding system built into Overcrowded is based on the [Unity NavMesh](https://docs.unity3d.com/Manual/nav-NavigationSystem.html) and internally uses the normal Unity pathfinding algorithm. This makes it very easy to move from a Unity `NavMeshAgent` to an Overcrowded `Navigator`. See [this guide](../HowTo/ReplaceNavMeshAgent.md) for how to migrate from a Unity `NavMeshAgent` to an overcrowded `EnhanceNavMeshAgent`.

### Using Overcrowded Navigator

Every Overcrowded agent includes a [`Navigator`](../../Reference/MonoBehaviours/Navigator) MonoBehaviour. This MonoBehaviour includes the `FindPath` methods which start a pathfinding job and returns a [`PathfindingTask`](../../Reference/Other/PathfindingTask/) object which represents the job. The job will run in the background over several frames, the `PathfindingTask` object can be polled to check if it is completed. Once the job is complete a [`PathfindingResult`](../../Reference/Other/PathfindingResult/) can be retrieved from the task object.

### Continued Reading

 - [How To: Find A Path](../../HowTo/FindPath) a simple tutorial on how to find a path from scripts.
 - [How To: Follow A Path](../HowTo/FollowPath) a simple tutorial on how to follow a path to a point.
 - [`Navigator`](../../Reference/MonoBehaviours/Navigator) reference documentation for the `Navigator` MonoBehaviour.
 - [`PathfindingTask`](../../Reference/Other/PathfindingTask/) reference documentation for the `PathfindingTask`.
 - [`PathfindingResult`](../../Reference/Other/PathfindingResult/) reference documentation for the `PathfindingResult`.