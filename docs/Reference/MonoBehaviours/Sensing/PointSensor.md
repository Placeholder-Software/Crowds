# PointSensor

This MonoBehaviour detects a single point as a danger and discourages steering towards it.

## Inspector

![EntityIdentity Inspector](../../../images/PointSensorInspector.png)

#### Name

The unique ID of this sensor. Used to identify this instance in scripts.

#### Point

The XZ position of the point.

#### Invert

If checked, all directions _away_ from the point will be detected as a danger. If unchecked the direction _towards_ the point will be detected as a danger.

#### Negative Weight

The importance of this negative sensor relative to other sensors.

#### Negative Min Distance

If the point is closer than this distance, the full `Negative Weight` will be used.

#### Negative Max Distance

If the point is farther than this distance, the sensor will be not detect it.

#### Delete/Add New

Create a new instance of this sensor or delete an existing instance.

## Scripting

#### `Create(string instanceName)`

Create a new sensor with the given name. If the name is `null` a random name will be chosen.

#### `TryGet(string instanceName)`

Try to get an existing sensor with the given name. Returns `null` if there is no sensor with that name.

#### `bool TryDelete(string instanceName)`

Try to delete the sensor with the given name. Returns `true` if a sensor with that name existed and was deleted.