# SteerForEvade

This MonoBehaviour causes an agent to steer away from the predicted future position of another agent. If the supplied `transform` is not an agent this is exactly equivalent to [`SteerForFlee`](../SteerForFlee). Also acts as a danger sensor discouraging steering directly towards the other agent.

## Inspector

![EntityIdentity Inspector](../../../../images/SteerForEvadeInspector.png)

#### Name

The unique ID of this steering action. Used to identify this instance in scripts.

#### Menace

The `transform` which this Agent is evading.

#### Max Prediction Time

If the `Menace` transform is another Agent it's position will be predicted this many seconds into the future and then this this agent will flee from that predicted position. This produces more responsive evasion than simply fleeing the agent directly.

#### Weight

The importance of this action relative to other steering actions.

#### Speed Type

The units for the `Speed` property. `Direct` means that the `Speed` setting is a speed in units/second. `Ideal` means that the `Speed` is a multiplier of the ideal speed (set in the `Navigator`). `Maximum` means that the `Speed` is a multiplier of the maximum speed (set in the `Navigator`).

#### Speed

The speed to move away from the target at. The units of this value depend on the `Speed Type` property.

#### Negative Weight

The importance of this negative sensor relative to other sensors. Set to zero to disable the sensor aspect of this steering action.

#### Negative Min Distance

If the `Menace` is closer than this distance, the full `Negative Weight` will be used.

#### Negative Max Distance

If the `Menace` is farther than this distance, the sensor will be not detect it.

#### Delete/Add New

Create a new instance of this steering action or delete an existing instance.

## Scripting

#### `Create(string instanceName)`

Create a new steering action with the given name. If the name is `null` a random name will be chosen.

#### `TryGet(string instanceName)`

Try to get an existing steering action with the given name. Returns `null` if there is no action with that name.

#### `bool TryDelete(string instanceName)`

Try to delete the steering action with the given name. Returns `true` if an action with that name existed and was deleted.