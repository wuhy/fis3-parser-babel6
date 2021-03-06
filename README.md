fis3-parser-babel6
======
[![Dependency Status](https://david-dm.org/wuhy/fis3-parser-babel6.svg)](https://david-dm.org/wuhy/fis3-parser-babel6) [![devDependency Status](https://david-dm.org/wuhy/fis3-parser-babel6/dev-status.svg)](https://david-dm.org/wuhy/fis3-parser-babel6#info=devDependencies) [![NPM Version](https://img.shields.io/npm/v/fis3-parser-babel6.svg?style=flat)](https://npmjs.org/package/fis3-parser-babel6)

> A babel 6 parser for fis3

## How to use

### Install

```shell
npm install fis3-parser-babel6 --save-dev
```

### Add configure to fis-conf.js

```js
// require the parser plugin and specify the parser
fis.require('parser-babel6').parser = require('babel-core');

fis.match('/src/**.js', {
    parser: fis.plugin('babel6', {
        // babel options
    })
});
```

By default, the babel helper api used information is saved to `file.extras.babelHelpers`. If you using [babel-plugin-external-helpers plugin](https://github.com/wuhy/fisx-prepackager-babel) plugin, you can lookup the used information from file `extras` property.

If the processed fis file has `disableBabel` property set `true`, the parser will ignore this file.

### Options

* speed - `boolean` `optional`: `experiment`, if you using npm2 to manage the dependencies, you can enable this option to speed up the babel startup time

* more babel options, please refer [babel](https://babeljs.io/docs/usage/api/#options)

