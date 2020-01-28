!!! warning
    This article mentions the Unity ECS. Although Crowds uses the ECS internally you don't need to understand anything about the ECS to use Crowds!

# BaseComponentProxyBehaviour

This is an abstract class which is used as the base for most behaviours. **You do not need to use this class unless you are extending Crowds.**

The class manages a set of ECS components which are controlled by the behaviour. The underlying components are managed so that they can easily be modified through serialization (at design time in the editor), at initialisation time (before the Entity representation is created) and at runtime (directly reading/writing the ECS data). It also handles automatically setting up and tearing down the components appropriately.

## Wrapping A Component

To use this class to add a component to the ECS version of a gameObject you need to do five things:

1. Create A new behaviour
2. Create nested `Component` class
3. Create field for new component class
4. Register it
5. Expose properties

```csharp
public class ANewThing                  // (1) Define a MonoBehaviour to add to a gameObject
    : BaseComponentProxyBehaviour
{

    [Serializable]                      // Must be `Serializable` for editing to work
    private class MyComponentWrapper    // (2)
        : Component<MyComponent>        // Pass in your component type as generic parameter
    {
        public MyComponentWrapper()
            : base(true)                // Boolean indicates if this component is enabled by default
        {   
        }
    }

    // (3) Create an instance of the component wrapper
    [SerializeField] private MyComponentWrapper _myComponentWrapper = new MyComponentWrapper();

    // (4) Register the component wrapper with the management system
    protected override void RegisterComponents()
    {
        Register(_myComponentWrapper);
    }

    // (5) Expose properties of the component
    public float SomeValue
    {
        // To get the component data read it directly from the `Value` field
        get {
            return _myComponentWrapper.Value.SomeValue;
        }

        // To set the component data copy it, modify it and write it
        set {
            var v = _myComponentWrapper.Value;  // Read/Copy
            v.SomeValue = value;                // Modify
            _myComponentWrapper.Value = v;      // Write
        }
    }
}
```

This basic pattern allows you to manage ECS components without worrying about the details of serialization, initialisation and teardown.