# PathfindingTask

This structure represents a pathfinding job which is still running.

## Script Properties

### IsComplete

Indicates if the pathfinding task is complete, `TryGetResult` will return a value once this is true.

### IsDisposed

Indicates if this task has been disposed. A result will never be returned once `IsDisposed` is `true`.

## Script Methods

### [PathfindingResult](/Reference/Other/PathfindingResult)? TryGetResult()

Attempts to retrieve a result from this task. Will return null until the task is complete. Once `TryGetResult` has returned a value the task is automatically disposed and it will not return a result again.

### Dispose()

Cancels the pathfinding task. A result will never be returned once this has been called.