* Start of the project
* run npm init -y

* install extention stylelint for VSCode
* install stylelint package, run:
* `npm install --save-dev stylelint stylelint-config-standard stylelint-config-idiomatic-order stylelint-webpack-plugin`
* add .stylelintrc file
* add webpack plugin to your config
* `const StylelintPlugin = require('stylelint-webpack-plugin');`
* `module.exports = {`
* `  // ...`
* `  plugins: [new StylelintPlugin(options)],`
* `  // ...`
* `};`
* add npm script `"stylelint "**/*.{css,scss}" --fix"`
