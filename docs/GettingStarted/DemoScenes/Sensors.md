## Basic Steering Sensors

Overcrowded includes a demo scene for each basic steering sensor. Steering sensors tell an agent which directions _not_ to move in - an agent will not actively steer away from them but will simply avoid trying to steer towards them. These scenes can be found in the `Assets\Plugins\PlaceholderSoftware\Crowds\Demos\Basics` folder.

The **[BasicCircleSensor](../../Reference/Sensing/CircleSensor)** scene demonstrates an agent using arrival steering to move in a straight line towards a point. The circular sensor causes the agent to avoid the middle of the scene.

The **[BasicGameObjectSensor](../../Reference/Sensing/GameObjectSensor)** scene demonstrates an agent using arrival steering to move in a straight line towards a point. The game object sensor functions exactly the same as the circle sensor, but it is centred on a GameObject in the scene.

The **[BasicLineSensor](../../Reference/Sensing/LineSensor)** scene demonstrates an agent using arrival steering to move in a straight line towards a point. The line sensor causes the agent to avoid a line across the middle of the scene.

The **[BasicPointSensor](../../Reference/Sensing/LineSensor)** scene demonstrates an agent using arrival steering to move in a straight line towards a point. The point sensor causes the agent to avoid a single point in the middle of the scene.