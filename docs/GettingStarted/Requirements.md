## Unity Package Manager

Overcrowded requires several packages installed from the Unity package manager:

 - [Burst (1.3.9)](https://docs.unity3d.com/Packages/com.unity.burst@latest/)
 - [Collections (0.9.0 - preview.6)](https://docs.unity3d.com/Packages/com.unity.collections@latest/)
 - [Entities (0.11.2 - preview.1)](https://docs.unity3d.com/Packages/com.unity.entities@latest/)
 - [Jobs (0.2.10 - preview.13)](https://docs.unity3d.com/Packages/com.unity.jobs@latest/)
 - [Mathematics (1.2.1)](https://docs.unity3d.com/Packages/com.unity.mathematics@latest/)
 - [Unity.Physics (0.4.1)](https://docs.unity3d.com/Packages/com.unity.physics@latest/)

Overcrowded has been built and tested to work with the listed versions. As new versions of these packages are released we will update to support them as soon as possible. If you encounter a compatibility issue with any of these packages please report it on the [issue tracker](https://github.com/Placeholder-Software/Crowds/issues) and we'll fix it right away.

!!! note
    Overcrowded is built with DOTS, ECS and the Job System for the best performance with large numbers of agents.
    However, **you do not have to understand ECS** to use Overcrowded! Setup of agents is done with classic MonoBehaviours and GameObjects.

## Unity Version

Overcrowded will support Unity LTS versions and the latest Unity TECH version starting with `2019.4`.

If you have a compatibility problem with a supported version of the Editor please contact us through [Discord](https://placeholder.software/discord), or report it on the [issue tracker](https://github.com/Placeholder-Software/Crowds/issues).