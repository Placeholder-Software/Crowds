# SteerForWander

This MonoBehaviour causes an agent to steer randomly. It is not pure random noise as that would look very jittery and not at all natural.

## Inspector

![SteerForWander Inspector](../../../../images/SteerForWanderInspector.png)

todo: take that screenshot ^

#### Use Worley Noise

Select if the noise used will be simplex or worley. Simplex noise is more random - the agent will smoothly change direction most of the time. Worley noise is more irregular - the agent will wander a short distance in a direction before more rapidly turning to a new direction.

#### Scale

The size of the wander. A small scale will rapidly change direction very frequently. A large scale will slowly change direction more rarely.

#### Weight

The Weight of this steering behaviour in the weighted average with all other steering behaviours.

#### Speed Type

The units for the `Speed` property. `Direct` means that the `Speed` setting is a speed in units/second. `Ideal` means that the `Speed` is a multiplier of the ideal speed (set in the `Navigator`). `Maximum` means that the `Speed` is a multiplier of the maximum speed (set in the `Navigator`).

#### Speed

The speed to wander at. The units of this value depend on the `Speed Type` property.

todo: refactor for buffer steering