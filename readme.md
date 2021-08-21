# Start of the project

### NPM installation
```
npm init -y
```
***
### stylelint
- install extention stylelint for VSCode
- install stylelint package

```
npm install --save-dev stylelint stylelint-config-standard stylelint-config-idiomatic-order stylelint-webpack-plugin
```

- add .stylelintrc file
- add webpack plugin to your config
```javascript
const StylelintPlugin = require('stylelint-webpack-plugin');
module.exports = {
  // ...
  plugins: [new StylelintPlugin(options)],
  // ...
};
```
- add npm script

```json
"stylelint": "stylelint \"**/*.{css,scss}\" --fix"
```
