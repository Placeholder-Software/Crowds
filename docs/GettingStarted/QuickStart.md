## Getting Started (MonoBehaviours)

1. After installing Crowds from the Unity asset store, check that you have the [requirements](../Requirements/) installed.
2. Once you have Crowds properly installed, have a look at the demo scenes included in the package. They will walk you through the basics of the asset.
3. Create a new gameObject in your scene, add the `Convert To Entity`, `Entity identity` and `Navigator` components.
4. Start adding steering behaviours to control the movement of the agent around the scene.

If you are unsure how to achieve the type of movement you want have a look at the `How To` section of this documentation to see if there is a tutorial covering what you need. If there isn't then come and ask for help on [Discord](https://placeholder.software/discord).

### Crowds And Unity DOTS

Crowds _internally_ uses the Unity "Data Oriented Tech Stack" (ECS, Jobs, Burst compiler) to simulate all the agents efficiently. However, to use Crowds **you do not need to understand DOTS**, all the complexity of it is contained within Crowds and is presented as a set of easy to use MonoBehaviours. If you are not using the ECS to build your game you can simply ignore any parts of this documentation which mention the ECS.