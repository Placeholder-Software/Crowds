# GameObjectSensor

This MonoBehaviour detects another GameObject as a danger and discourages steering towards it. This is similar to a [PointSensor](../PointSensor.md) where the point is always at the location of a particular GameObject.

## Inspector

![EntityIdentity Inspector](../../../../images/GameObjectSensorInspector.png)

#### Name

The unique ID of this sensor. Used to identify this instance in scripts.

#### Menace

The GameObject which will be detected as a danger.

#### Invert

If checked, all directions _away_ from the GameObject will be detected as a danger. If unchecked the direction _towards_ the GameObject will be detected as a danger.

#### Negative Weight

The importance of this negative sensor relative to other sensors.

#### Negative Min Distance

If the GameObject is closer than this distance, the full `Negative Weight` will be used.

#### Negative Max Distance

If the GameObject is farther than this distance, the sensor will be not detect it.

## Scripting

#### `Create(string instanceName)`

Create a new sensor with the given name. If the name is `null` a random name will be chosen.

#### `TryGet(string instanceName)`

Try to get an existing sensor with the given name. Returns `null` if there is no sensor with that name.

#### `bool TryDelete(string instanceName)`

Try to delete the sensor with the given name. Returns `true` if a sensor with that name existed and was deleted.