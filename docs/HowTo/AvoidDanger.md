1. [Create an agent](../CreateAnAgent).
2. Add a [GameObjectSensor](../../Reference/MonoBehaviours/Sensing/GameObjectSensor).
3. Click `Add New` and give the sensor a unique name.
4. Drag the game object which represents the danger into the `Menace` field.
5. Set the `Negative Weight` to a value greater than zero. This controls how important this danger is _relative to other sensors_. A weight of `0` disables this sensor.
6. Set the `Negative Min Distance` to a distance where there is maximum danger. If the agent is this close (or closer) it will be sensing the full `Negative Weight` you have set.
7. Set the `Negative Max Distance` to a distance where there is no danger. If this agent is this far (or farther) there is no danger detected from this sensor.