## Basic Steering Actions

Overcrowded includes a demo scene for each basic zones. Zones affect all agents within the zone and can be used to tweak how agents move in certain areas of the scene. These scenes can be found in the `Assets\Plugins\PlaceholderSoftware\Crowds\Demos\Basics` folder.

The **[BasicNegativeZone](../../../Reference/MonoBehaviours/Zones/NegativeZone)** scene demonstrates a negative zone which acts as a danger sensor for agents inside it. The zone in this scene is configured to discourage movement along the length of the zone, but to allow movement directly across the zone.

The **[BasicPriorityZone](../../../Reference/MonoBehaviours/Zones/PriotityZone)** scene demonstrates a priority zone which increases the priority of agents inside it. When two agents are on a collision course lower priority agents will yield to higher priority agents.

The **[BasicUrgencyZone](../../../Reference/MonoBehaviours/Zones/UrgencyZone)** scene demonstrates an urgency zone which increases the urgency of agents inside it. Agents with a higher urgency act more selfishly to more effectively push their way through dense crowds.