# Overcrowded

**Overcrowded** makes it easy to control player and AI movement with a suite of context aware steering actions, a cutting edge local avoidance algorithm and automatic jobified multithreaded pathfinding.

([**Documentation**](https://placeholder-software.co.uk/overcrowded/docs/))
([**Discord**](https://discord.gg/gaCJeQkvcf))
([**Issue Tracker**](https://github.com/Placeholder-Software/Crowds))

## Context Aware Steering
Context aware steering allows blending of many actions without the indecisiveness seen in classic steering behaviours. Steering sensors are a novel systems which allows hinting where an agent _should not_ go, allowing more nuanced control from a greater variety of gameplay signals. Overcrowded includes a library of steering actions and sensors that can be used to build complex movement AI entirely in the editor.

## Cutting Edge Local Avoidance
Local avoidance subtly adjusts how agents move to make large crowds flow naturally. The unique _Time-Sampled Velocity Obstacles_ (TSVO) algorithm can find avoidance solutions in the densest and most chaotic of crowds. Where other algorithms will fail to find a solution, TSVO's multi-stage fallback, crossing avoidance, and intelligent sample selection ensures your agents (including players) can weave through any crowd.

## Ultimate Performance
Built on the [Data Oriented Technology Stack](https://unity.com/dots) (DOTS) but controlled through familiar GameObjects and inspectors: Overcrowded brings the latest performance advances while allowing developers to leverage their existing Unity expertise. Overcrowded automatically runs all steering evaluation, pathfinding and local avoidance on Unity's high performance multi-threaded job system.

## Pathfinding
Leverage your existing Unity NavMesh based scenes. Overcrowded integrates Unity's latest DOTS-compatible pathfinder API with our own path query runtime to offload pathfinding work onto the multi-threaded job system. Simultaneously compute hundreds of paths and never worry about the frame rate.

## Get Going in Minutes
Overcrowded can be dropped into your game and configured entirely with drag-and-drop MonoBehaviour scripts. With the drop-in replacement for Unity's _NavMeshAgent_ script you can get up and running in a matter of minutes. Comprehensive documentation and demo scenes will help you learn how to make the best use of all the available features.

## Complete Source Code
All of the C# source code for Overcrowded is included in the package, there are no closed source components.

todo (url): [Buy Now On The Asset Store ❤️](todo-store-link){: .md-button .md-button--primary }

---

# Learn More
## Concepts

 - [Context Aware Steering Actions](GettingStarted/SteeringActions)
 - [Scene Sensing](GettingStarted/SteeringSensors)
 - [Realtime Local Avoidance](GettingStarted/LocalAvoidance)
 - [Jobified Pathfinding](GettingStarted/PathfindingJobs)

## Getting Started

 - [Quick Start](GettingStarted/QuickStart)
 - [Dependencies](GettingStarted/Requirements)
 - [Demo Scenes](GettingStarted/DemoScenes)
 - [How To Create An Agent](HowTo/CreateAnAgent)
 - [How To Replace A Nav Mesh Agent](HowTo/ReplaceNavMeshAgent)

## Reference Docs

 - [Navigator](Reference/MonoBehaviours/Navigator)
 - [Steer For Arrival](Reference/MonoBehaviours/Steering/SteerForArrival)
 - [Circle Sensor](Reference/MonoBehaviours/Sensing/CircleSensor)
 - [Urgency Zone](Reference/MonoBehaviours/Zones/UrgencyZone)
 - [Enhanced Nav Mesh Agent](Reference/MonoBehaviours/EnhancedNavMeshAgent)