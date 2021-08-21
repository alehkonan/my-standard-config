# Start of the project

<<<<<<< HEAD
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
=======
**NPM installation**
- run `npm init -y`

**stylelint**
- install extention stylelint for VSCode
- install stylelint package
- run `npm install --save-dev stylelint stylelint-config-standard stylelint-config-idiomatic-order stylelint-webpack-plugin`
- add .stylelintrc file
- add webpack plugin to your config

>>>>>>> 507273213226125aecd5354a04dffa41012a5684
```javascript
const StylelintPlugin = require('stylelint-webpack-plugin');
module.exports = {
  // ...
  plugins: [new StylelintPlugin(options)],
  // ...
};
```
<<<<<<< HEAD
- add npm script

```json
"stylelint": "stylelint \"**/*.{css,scss}\" --fix"
```
=======

- add npm script `"stylelint "**/*.{css,scss}" --fix"`
>>>>>>> 507273213226125aecd5354a04dffa41012a5684
