Local Avoidance is one of the most important parts of achieving natural agent movement. The local avoidance system slightly adjusts the output from [Context Aware Steering Actions](../SteeringActions) to avoid collisions with other agents. This significantly improves the appearance of groups of agents moving in close proximity. Overcrowded includes a novel **Time Sampled Local Avoidance** algorithm which simultaneously chooses collision free movement directions for every agent in the scene.

![Local Avoidance Steering](../images/SteeringLocalAvoidance.png)

### Using Local Avoidance

Local Avoidance is built into the core [Navigator](../../Reference/MonoBehaviours/Navigator) MonoBehaviour. To use it simply [create an agent](../../HowTo/CreateAnAgent), open the [Navigator](../../Reference/MonoBehaviours/Navigator) inspector, turn on [`Block Other Agents`](../../Reference/MonoBehaviours/Navigator#block-other-agents) to make other agents avoid this agent and turn on [`Avoid Local Obstacles`](../../Reference/MonoBehaviours/Navigator#avoid-local-obstacles) to make this agent avoid nearby obstacles (e.g. other agents).

### Urgency

There will always be situations where a Local Avoidance algorithm will fail to find a collision free direction for some agents to move in. This can sometimes cause low priority agents to get stuck at the edges of a Crowd, failing to ever make any progress towards their destination. Overcrowded includes an innovative solution to this problem: Urgency.

Urgency increases when an agent is not making any progress and temporarily makes the agent more "selfish" - this allows it to push past the obstacle that was stopping it. This selfishness can help clear blockages in crowds and significantly improves the overall flow of agents through the scene even in areas where other Local Avoidance algorithms would fail.

To add Urgency to an agent simply add an [Urgency](../../Reference/MonoBehaviours/Urgency) MonoBehaviour alongside the [Navigator](../../Reference/MonoBehaviours/Navigator) MonoBehaviour.

### Configuring Local Avoidance

With the default settings local avoidance will improve the movement of all agents around the scene. However, you may want to configure specific agents to move in a different way. For example all NPCs should avoid collisions with the player character even if it means colliding with other NPCs.

All configuration is done by setting a range, not a specific value. The actual value used is randomly picked from the range. This means that if you spawn many agents from the same prefab they will all have slightly different configurations, this significantly improves the quality of movement of large groups of agents.

### Priority

When two agents are walking towards a collision they must both adjust their movement direction to avoid the collision. Priority controls how much each agent is willing to adjust their direction.

![Local Avoidance Steering](../images/LocalAvoidanceYield.webp)

If both of these agents have an _equal_ priority they will both adjust their direction the same amount (as shown above). If one agent has a slightly higher priority then it will adjust it's direction less than the agent with the lower priority. If one agent has a much higher priority (difference is greater than one) then it will not adjust it's direction at all, leaving the lower priority agent to to avoid the collision.

This can be used to create more "important" agents which other agents will try not to block. For example:
 - Important storyline NPCs can have a much higher priority than basic "crowd filler" NPCs
 - Boss NPCs can have a higher priority than basic enemy NPCs
 - Player characters can have higher priority than allied NPCs

## Personality

There are two different ways to configure the remaining Local Avoidance parameters: personality configuration or advanced configuration.

When `Personality Auto Configuration` is enabled all of the Local Avoidance parameters are configured from just two parameters, "Carefulness" and "Extraversion". A very "careful" agent will try very hard to avoid collisions, even if it means frequently changing direction and moving erratically. A very "extraverted" agent will try very hard to push through other agents, even if it means extra collisions.

When `Personality Auto Configuration` is disabled all of the Local Avoidance parameters can be configured directly. See the [`Navigator`](../../Reference/MonoBehaviours/Navigator#personal-space-radius) documentation for further detail on these settings.