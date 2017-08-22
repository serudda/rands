## Scenes

A scene is a page of your application. You can see a scene just like any component, but I like to separate them into their own folder.

If you use React-Router or React Native Router, you can import all your scenes in your main index.js file and setup your routes.

With the same principle components can be nested, you can also nest a scene into a scene, and also define components or services into a scene. You have to remember that if you decide to define something into a scene, you can only use it within the scene folder itself.

Example:

```
/src
  /scenes
    /Home
      /components
        /ButtonShare
          /index.js
      /index.js
    /Sign
      /components
        /ButtonHelp
          /index.js
      /scenes
        /Login
          /components
            /Form
              /index.js
            /ButtonFacebookLogin
              /index.js
          /index.js

        /Register
          /index.js
      /index.js
```

- *Home* has a component ButtonShare, it can only be used by the Home scene.
- *Sign* has a component ButtonHelp. This component can be used by Login or Register scenes, or by any components defined in those scenes.
- *Form* component uses ButtonHelp internally, this is authorized because ButtonHelp is defined by a parent.
- The *Register* scene cannot use any of the components defined in Login, but it can use the ButtonHelp.
