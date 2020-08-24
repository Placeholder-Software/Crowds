# Synchroniser

This Monobehaviour sychronises the Crowds simulation and the GameObjects in the scene.

## Inspector

![EntityIdentity Inspector](../../../../images/SynchroniserInspector.png)

#### Preset

These presets automatically configure the other settings for common scenarios:

 - **No Sync**: Disables all other settings. No data will be copied between the Crowds simulation and the scene GameObjects.
 - **Initial Sync Only**: Transfrom will be copied from the GameObject into the simulation at the start. No per-frame syncing.
 - **GameObject Is Master**: Initial position is copied from GameObject. The simulation transform is overwritten with the GameObject transform every frame.
 - **Simulation Is Master**: Initial position is copied from GameObject. The GameObject transform is overwritten with the Simulation transform every frame.
 - **Custom**: Unlocks the other settings to allow a custom configuration.

#### Startup

These settings control which transform values (position and rotation) are copied between the GameObject and the simulation when the GameObject is first created. They are only enabled if the `Preset` is set to `Custom`.

##### GameObject Transform ⇒ Simulation

The transform of the GameObject will be copied into the simulation.

##### Simulation ⇒ GameObject

The simulation transform will be copied into the GameObject

#### Every Frame

These settings control which transform values (position and rotation) are copied between the GameObject and the simulation every frame. They are only enabled if the `Preset` is set to `Custom`.

##### GameObject Transform ⇒ Simulation

The GameObject transform will be copied into the simulation. When this is enabled the GameObject will not move and the simulation agent will stay wherever the GameObject is. Use this if you are moving the GameObject is response to the Crowds simulation with another script (e.g. [see this guide](/HowTo/AnimatedAgents)).

##### Simulation ⇒ Translation

The Simulation `Translation` will be copied into the GameObject transform. The gameObject will move (but not rotate) in resposne to the simulation.

##### Simulation ⇒ Rotation (Forward)

The forward (XZ) component of the simulation rotation will be copied into the GameObject transform. The GameObject turn (but not move) in response to the simulation.

##### Simulation ⇒ Rotation (Up Axis)

The Up component of the simulation rotation (perpendicular to the NavMesh) will be copied into the GameObject transform. The GameObject will be aligned with the floor in response to the simulation.