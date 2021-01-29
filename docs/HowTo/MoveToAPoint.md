## Without Pathfinding

1. [Create an agent](../CreateAnAgent).
2. Add a [SteerForArrival](../../Reference/MonoBehaviours/Steering/SteerForArrival) component.
3. Click `Add New` and give the steering action a unique name.
4. Set the target X/Y position in the `Target` fields.
5. Choose a `Slowing Distance`, this sets how far before arriving at the target the agent starts slowing to a stop.
6. Set the `Weight` to `1.0`. this sets how important this steering action is _relative to other steering actions_. A weight of `0` disables this steering action.
7. Set the `Speed Type` to `Ideal` and the `Speed` to `1`. This will make the agent move to target target point at the [Ideal Speed](../../Reference/MonoBehaviours/Navigator#ideal-speed).