## Basic Steering Actions

Overcrowded includes a demo scene for each basic steering action. Steering actions tell an agent which direction and how fast to move. Overcrowded combines all of these steering actions into one context and then picks the single best direction. These scenes can be found in the `Assets\Plugins\PlaceholderSoftware\Crowds\Demos\Basics` folder.

The **[BasicSteerForAlignment](../../../Reference/MonoBehaviours/Steering/SteerForAlignment)** scene demonstrates alignment steering which aligns the agent with the movement direction of nearby agents. This scene includes several other agent which simply walk in a straight line, to influence the main agent as it passes by.

The **[BasicSteerForArrival](../../../Reference/MonoBehaviours/Steering/SteerForArrival)** scene demonstrates arrival steering which moves towards a point and comes to a stop when it arrives.

The **[BasicSteerForCohesion](../../../Reference/MonoBehaviours/Steering/SteerForCohesion)** scene demonstrates cohesion steering which moves an agent towards the average position of nearby agents. This scene includes several other agents which simply move to randomly generated points, the main agent stays in the middle of them.

The **[BasicSteerForEvade](../../../Reference/MonoBehaviours/Steering/SteerForEvade)** scene demonstrates evasion steering which predicts the future position of another agent and steers to avoid it. The scene includes a player controlled agent which the other agent attempts to evade.

The **[BasicSteerForFlee](../../../Reference/MonoBehaviours/Steering/SteerForFlee)** scene demonstrates flee steering which moves directly away from a specific point.

The **[BasicSteerForGoal](../../../Reference/MonoBehaviours/Steering/SteerForGoal)** scene demonstrates goal steering which finds a path from the agent to the given destination and then follows the path to it.

The **[BasicSteerForInterpose](../../../Reference/MonoBehaviours/Steering/SteerForInterpose)** scene demonstrates interpose steering which steers an agent to stay between two other agents.

The **[BasicSteerForPursue](../../../Reference/MonoBehaviours/Steering/SteerForPursue)** scene demonstrates pursuit steering which predicts the future position of another agent and steers towards it. The scene includes a player controlled agent which the other agent attempts to pursue.

The **[BasicSteerForTargetSpeed](../../../Reference/MonoBehaviours/Steering/SteerForTargetSpeed)** scene demonstrates speed steering which steers an agent at a given speed in no particular direction. The agent in this scene has "local avoidance" enabled to steer away from walls which block it's path.

The **[BasicSteerForVelocity](../../../Reference/MonoBehaviours/Steering/SteerForVelocity)** scene demonstrates velocity steering which steers an agent in a specific direction. The agent in this scene is player controlled, the `Steer User Input` script copies the velocity into the `TargetVelocity Steering` behaviour.

The **[BasicSteerForWander](../../../Reference/MonoBehaviours/Steering/SteerForWander)** scene demonstrates wander steering which steers an agent randomly.