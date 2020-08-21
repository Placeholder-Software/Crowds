# SteerForCohesion

This MonoBehaviour causes an agent to steer in the same direction as nearby agents.

## Inspector

![EntityIdentity Inspector](../../../../images/SteerForCohesionInspector.png)

#### Name

The target position (in 2D space) that the agent is walking towards. For example if you have a `transform` to walk towards you would set this to the `XZ` position of the `transform`.

#### Weight

The Weight of this steering behaviour in the weighted average with all other steering behaviours.

#### Speed Type

The units for the `Speed` property. `Direct` means that the `Speed` setting is a speed in units/second. `Ideal` means that the `Speed` is a multiplier of the ideal speed (set in the `Navigator`). `Maximum` means that the `Speed` is a multiplier of the maximum speed (set in the `Navigator`).

#### Speed

The speed to move away from the target at. The units of this value depend on the `Speed Type` property.

#### Max Prediction Time

todo

#### Arrival Distance

todo

#### Max Distance

todo

### Add New/Delete

todo