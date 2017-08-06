## Note on debugging

- CMD + D / Ctrl + M ' opens In-App dev menu.
  - Debug JS remotely' command opens a browser window
- open dev tools and console log and invoke debugger as you would for web app

## Configuring custom babelrc

In order to use the main component on both platforms, move it's code to a separate file and import if to both .ios.js and .android.js indexes.

  - add ```babel-preset-react-native-stage-0``` and ```babel-root-import``` to dev-dependencies
    - stage-0 are not-yet-standard features
    - root-import allows for simpler relative import paths (define the root and use ~ sign in imports instead)
