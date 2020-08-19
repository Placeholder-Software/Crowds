## Getting Started

1. Install Crowds from the Unity Asset Store.
2. Install the [required packages](../Requirements/).
3. Follow the [How To: Create An Agent](..HowTo/CreateAnAgent/) guide.
4. Add [steering behaviours](SteeringBehaviours/) to control the movement of the agent around the scene.
5. Add [sensors](SteeringBehaviours#Danger%20Sensors) to make the agent avoid things in the scene.

If you are unsure how to achieve the type of movement you want have a look at the `How To` section of this documentation to see if there is a tutorial covering what you need. If there isn't then come and ask for help on [Discord](https://placeholder.software/discord).

## Basic Concepts

The **Getting Started** section 

todo explain and link getting started stuff

## Demo Scenes

Crowds includes a number of demo scenes which introduce the basic concepts of the asset and demostrate how to create some common scenarios. Get started with these demos by running the `Start Here` scene in the `Assets/Plugins/PlaceholderSoftware/Crowds/Demos` folder.

todo: link all demos

### Crowds And Unity DOTS

Crowds _internally_ uses the Unity "Data Oriented Tech Stack" (ECS, Jobs, Burst compiler) to simulate all the agents efficiently. However, to use Crowds **you do not need to understand DOTS**! All the complexity of it is contained within Crowds and is presented as a set of easy to use MonoBehaviours. If you are not using the ECS to build your game you can simply ignore any parts of this documentation which mention the ECS.