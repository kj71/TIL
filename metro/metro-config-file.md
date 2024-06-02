In React Native, we may find a file `metro.config.js`.  In this file, we either export a Javascript object or a function (which is called internally) to return a Javascript object. This object is the Metro config.

> If we export the object it will be used on top of the Metro's internal default configs. 
However, if we export the function, then Metro, by itself, will not apply those default configs. However we can get those defaults as parameter in the function.

Below is a sample config structure.

```javascript
{
  transformer: {
    getTransformOptions: async () => ({
      transform: {
        // official doc regarding this not found as of now
        experimentalImportSupport: false,
        // checks for inline requires. However, may not work as expected.
        // Check this: https://github.com/facebook/metro/issues/909
        inlineRequires: true,
      },
    }),
  },
  resolver: {
    // to include the asset extensions that are to be referenced my the Metro.
    //By default, Metro has a list of widely used asset extensions that it references (eg: png, jpeg, pdf, mp3, mp4).
    assetExts: [],
    // to include the source code file extensions that are to be referenced my the Metro.
    // By default, Metro references files like ts, tsx, js, jsx, json in some order.
    sourceExts: [],
  },
  // for the source code folders that may not be located in the root project.
  watchFolders: [],
  // can be used for things like specifying the port from where Metro is to listen, changing the urls Metro gets.
  server: {
    // to make changes to the url before Metro gets it.
    rewriteRequestUrl: (url) => {
      return url;
    },
  },
}
```


