## Components

Components defined at the root level of your project, in the components folder, are global and can be used anywhere in your application. But if you decide to define a new component inside another component (nesting), this new component can only be used its direct parent.

Example:

```
/src
  /components
    /Button
      /index.js
    /Notifications
      /components
        /ButtonDismiss
          /index.js
      /actions.js
      /index.js
      /reducer.js
```

- *Button* can be used anywhere in your application.
- *Notifications* can also be used anywhere. This component defines a component ButtonDismiss. You cannot use ButtonDismiss anywhere else than in the Notifications component.
- *ButtonDismiss* uses Button internally, this is authorized because Button is defined at the root level of components.
