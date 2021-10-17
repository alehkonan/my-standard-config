# Start of the webpack project

### NPM installation
```
npm init -y
```
***
### Webpack installation
```
npm i -D webpack webpack-cli @webpack-cli/generators
```
To generate webpack-config-file run next command and answer questions
```
npx webpack init
```
Then you should choose to overwrite or not package.json and readme.md files
Then you can add another plugins and rules into webpack.config.js
***
### React
If you want to use React run
```
npm i react react-dom react-router-dom
```
To use SVG as React Component install svg-react-loader
```
npm i -D svg-react-loader
```
then add loader for webpack.config.js
```javascript
module: {
  rules: [
    {
      test: /\.svg$/,
      exclude: /node_modules/,
      loader: "svg-react-loader",
    },
  ],
},
```
then you can import icons and use them as components
```javascript
import Icon from 'icon.svg';

const Component = () => {
  return <Icon />
}
```
### Add Typescript to React
if you use typescript also install types
```
npm i -D @types/react @types/react-dom @types/react-router-dom
```
***
### ESLint
Install extension for VSCode
Install eslint with eslint-webpack-plugin
```
npm i -D eslint eslint-webpack-plugin
```
Add ESLintPlugin to webpack config
```javascript
const ESLintPlugin = require('eslint-webpack-plugin');

module.exports = {
  // ...
  plugins: [new ESLintPlugin({
    fix: true,
  })],
  // ...
};
```
Then you should create .eslintrc file
The best way is to use command and answer questions
```
npx eslint --init
```
then you can add file .eslintignore and add there **webpack.config.js**
- add npm script

```json
"eslint": "eslint \"**/*.{ts,tsx,js,jsx}\" --fix"
```
### Fixing eslint problems with React and typescript
Add this rules and settings to .eslintrc file
```json
{
  "rules": {
    "no-use-before-define": "off",
    "@typescript-eslint/no-use-before-define": ["error"],
    "react/jsx-filename-extension": [ "warn", {"extensions": [".tsx"]} ],
    "import/extensions": [
      "error",
      "ignorePackages", {
        "ts": "never",
        "tsx": "never"
      }
    ],
    "no-shadow": "off",
    "@typescript-eslint/no-shadow": ["error"],
    "@typescript-eslint/explicit-function-return-type": [
      "error", {
        "allowExpressions": true
      }
    ],
    "react-hooks/rules-of-hooks": "error",
    "react-hooks/exhaustive-deps": "warn",
    "import/prefer-default-export": "off",
    "react/prop-types": "off"
  },
  "settings": {
    "import/resolver": {
      "node": {
        "extensions": [".js", ".jsx", ".ts", ".tsx"]
      }
    }
  }
}
```
add compiler options to .tsconfig.json
```json
"compilerOptions": {
  "jsx": "react",
  // aliases
  "baseUrl": ".",
  "paths": {
    "@components/*": ["components/*"],
  }
}
```
***
### Prettier
It`s better to install prettier plugin to eslint to avoid conflicts
install prettier with it`s plugin for eslint
```
npm i -D prettier eslint-config-prettier
```
Then add "prettier" to .eslintrc file
```json
{
  "extends": [
    "some-other-config-you-use",
    "prettier"
  ]
}
```
***
### Stylelint
- install extension stylelint for VSCode
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
  plugins: [new StylelintPlugin({
    fix: true,
  })],
  // ...
};
```
- add npm script

```json
"stylelint": "stylelint \"**/*.{css,scss}\" --fix"
```
