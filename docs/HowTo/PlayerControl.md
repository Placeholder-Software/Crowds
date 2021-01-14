Agents can be controlled by player input by using the [SteerForTargetVelocity](/Reference/MonoBehaviours/Steering/SteerForTargetVelocity) behaviour and a custom script which reads player [Input](https://docs.unity3d.com/ScriptReference/Input.html) and sets the `SteeringVector` property. There is a basic example script included in the package at `Assets/Plugins/PlaceholderSoftware/Crowds/Demos/Content/Scripts/SteerUserInput.cs`.

The [Navigator](/Reference/MonoBehaviours/Navigator) behaviour of a player driven agent should be configured to to move through the crowd very aggressively so that other agents tend to move out of it's way, this keeps the movement of the agent closely tied to the input from the player. This can be achieved in two ways.

### Local Avoidance

Agents are influenced by [`Local Avoidance`](/GettingStarted/LocalAvoidance/) which influences their movement to avoid obstacles such as walls and other agents. However this can cause the player character to make movements which the player did not command.

The simplest way to solve this is to disable `Avoid other Agents` and enable `Block Other Agents`. In this configuration other agents will avoid the player character but the player character will completely ignore other agents - it will move exactly as commanded by the `SteerForTargetVelocity` behaviour. This creates the most responsive movement but will cause the player character to collide with other agents if the input changes suddenly.

An better solution is to tweak the `Navigator` parameters so that it avoids other agents just a small amount, this creates a more natural looking agent which moves through the crowd smoothly but still responds quickly to player movement.

 - Increase `Priority` to a very high value, this will cause other agents to do most (but not all) of the work of avoiding a collision.
 - Reduce `Carefulness` to a very low value, this will cause the agent to be less erratic as it avoids other agents.
 - Increase `Extraversion` to a very high value, this will cause other agents to prioritise avoiding this agent more than other agents.

A more advanced solution could tweak these parameters at runtime in response to input/gameplay events. For example when walking the player character can have a less aggressive configuration, when running the values can be boosted to more extreme values.