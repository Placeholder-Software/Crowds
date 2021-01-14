!!! note
    To find a path without following it, follow this [guide](../FindPath) instead.

1. To use pathfinding you must check `Enable Pathing` on the `Navigator` behaviour.
2. Add a `Steer For Goal` behaviour to the agent.
3. Set a destination for the agent. There are two ways to do this:
    - Set the [`GoalPosition`](../../Reference/MonoBehaviours/Navigator/#goalposition) property on the `Navigator` behaviour from a script.
    - Add a [`Goal`](../../Reference/MonoBehaviours/Goal) behaviour to the agent and set a `transform` as the destination.