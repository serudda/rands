## Services

Not everything can be a component, and you will need to create independent modules that can be used by your components or scenes.

You can see a service like a self-contained module where you will define the core business logic of your application. This can eventually be shared between several scenes or even applications, such as a web and native version of you app.

Example:

```
/src
  /services
    /api
      /services
        /handleError
          /index.js
      /index.js
    /geolocation
    /session
      /actions.js
      /index.js
      /reducer.js
```

I recommend you to create services to manage all api requests. You can see them as a bridge/an adapter between the server API and the view layer (scenes and components) of your application. It can take care of network calls your app will make, get and post content, and transform payloads as needed before being sent or saved in the store of your app (such as Redux). The scenes and components will only dispatch actions, read the store and update themselves based on the new changes.
