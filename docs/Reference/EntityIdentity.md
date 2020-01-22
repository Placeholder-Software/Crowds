# EntityIdentity

This MonoBehaviour automatically maintains a connection between a GameObject in the scene and an ECS Entity which is used in the simulation.

## Inspector

![EntityIdentity Inspector](/images/EntityIdentityInspector.png)

#### Keep Alive

If this is **not** checked then the underlying Entity will automatically be deleted when this EntityIdentity MonoBehaviour is deleted.

## Script Properties

#### Entity

Get the entity which represents this gameObject. Will be `default` value when `IsCreated` is `false`.

#### EntityManager

The EntityManager used to create the entity. Will be `null` when `IsCreated` is `false`.

#### IsCreated

Indicates if the Entity for this gameObject has been created yet.

#### KeepAlive

If set to false the Entity will be deleted when `OnDestroy` runs for this Monobehaviour.