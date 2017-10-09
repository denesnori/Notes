## Webpack

- is a module bundler.

#### webpack.config.js

- contains build configuartion, loaders, and other build specific info.

Simplest:
```
module.exports = {
  entry: "./app.js", // file or array of files that we want to include in the build
  output: { // object,  containing the output configuration
    filename: "bundle.js" // this time we only the name of the build file
  }
}
```
To run the build run it in the command line:
```
webpack
```

#### Loader params

- test: regexp, select which files we should run the laoder on
- exclude: files the loader should ignore. eg.: node_modules
- loader: the name of the loader, we are going to use.
- query: options to the loader
- cacheDirectory: defaults to false. A repo where we want to save the results.
-presets:

#### Building React with webpack

Note: loaders are from webpack1, rules are from webpack2. Loaders might be deprecated soon.

```babel-loader``` converts JS written in ES6 to browser readable ES5.


```
module.exports = {
  entry: "./app.js", // string ,object, or array of files that we want to include in the build
  output: { // object,  containing the output configuration
    filename: "bundle.js" // this time we only the name of the build file
  },
  module: {
    loaders: [
      {
        test: /\.jsx?$/,
        exclude: /build|lib|node_modules/,
        loaders: ['babel-loader'],
        /*query: { // can add them to .babelrc instead
        cacheDirectory: true,
        presets: ['react', 'es2015']
      }*/
      }
    ]
  }
}
```


### Plugins

- additional node modules that wok on the resulting bundle
- eg. ```uglifyJSPlugin``` takes the bundle.js, minimizes it, and obfuscates the contents to decrease the file size.

#### Loaders vs Plugins

Loaders work at the individual file level either during or before the bundle is generated. While plugins work at the bundle or chunk level and usually work at the end of the generation process.

## References
1. (Beginners guide to webpack)[https://medium.com/javascript-training/beginner-s-guide-to-webpack-b1f1a3638460]
2. (Webpack the confusing parts)[https://medium.com/@rajaraodv/webpack-the-confusing-parts-58712f8fcad9]
