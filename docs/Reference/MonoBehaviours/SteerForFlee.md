# SteerForFlee

This MonoBehaviour causes an agent to steer directly away from a target point.

## Inspector

![EntityIdentity Inspector](../images/SteerForFleeInspector.png)

#### Target

The position which this Agent is fleeing from.

#### Weight

The Weight of this steering behaviour in the weighted average with all other steering behaviours.

#### Speed Type

The units for the `Speed` property. `Direct` means that the `Speed` setting is a speed in units/second. `Ideal` means that the `Speed` is a multiplier of the ideal speed (set in the `Navigator`). `Maximum` means that the `Speed` is a multiplier of the maximum speed (set in the `Navigator`).

#### Speed

The speed to move away from the target at. The units of this value depend on the `Speed Type` property.