Overcrowded includes a Local Avoidance system which attempts to tweak the path of all agents to avoid collisions. However this does not always provide satisfactory results and some extra hand-tweaking is required.

## Urgency

[Urgency](../GettingStarted/LocalAvoidance#urgency) is a parameter which increases rapidly when an agent is failing to move in the direction it wants. As an agent becomes more urgent it's priority increases, which makes it less willing to yield to other agents. A very urgent agent will create an invisible obstacle which other agents avoid, opening up a gap for the urgent agent to move into.

If you have problems with agents failing to make progress because other agents are blocking their path, consider adding an [Urgency](../Reference/MonoBehaviours/Urgency) behaviour. Urgency is very cheap to calculate and in general should be added to all agents.

## Urgency Zone

An [Urgency Zone](../Reference/MonoBehaviours/Zones/UrgencyZone) increases the urgency of an agent which is within the zone.

If you have an area of the map which agents are getting stuck in because of large numbers of other agents getting in their way consider adding an urgency zone which covers the agent getting stuck.

## Priority Zone

A [Priority Zone](../Reference/MonoBehaviours/Zones/PriorityZone) is very similar to an urgency zone - agents inside the zone will have increase "priority" and will become less willing you yield to other agents. Unlike an urgency zone high priority does not create the invisible obstacles to push apart the crowd.

If you have an area of the map which agents are getting stuck in because of higher priority agents taking precedence consider adding a priority zone which covers the agent getting stuck.

## Negative Zone

A [Negative Zone](../Reference/MonoBehaviours/Zones/NegativeZone) discourages flow in certain directions.

if you have an area of the map where agents are causing a problem because they are moving in certain directions (e.g. across a busy corridor, instead of along it) consider adding a negative zone to discourage the troublesome direction.