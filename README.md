# Storybook breaking Gridsome

This repository demonstrates how installing Storybook will break Gridsome. It doesn't show the solution (yet, hopefully).

To set up this project, I ran the following commands:

`gridsome create storybookBreakingGridsome`

`cd storyBookBreakingGridsome`

`yarn develop`

At this stage Gridsome is work as expected, but then I want to add Storybook:

`npx -p @storybook/cli sb init --type vue`

`yarn develop`

The build fails, with the following errors:

```
 ERROR  Failed to compile with 63 errors                                                                                                                                    11:51:57 AM

These dependencies were not found:

* core-js/modules/es6.array.filter in ./node_modules/gridsome/app/router.js, ./node_modules/gridsome/app/components/Link.js and 2 others
* core-js/modules/es6.array.for-each in ./node_modules/gridsome/app/head.js, ./node_modules/gridsome/app/router.js and 5 others
* core-js/modules/es6.array.from in ./node_modules/gridsome/app/directives/image.js
* core-js/modules/es6.array.index-of in ./node_modules/gridsome/app/utils/class.js
* core-js/modules/es6.array.is-array in ./node_modules/gridsome/app/router.js, ./node_modules/gridsome/app/utils/class.js
* core-js/modules/es6.array.map in ./node_modules/gridsome/app/entry.client.js, ./node_modules/gridsome/app/router.js
* core-js/modules/es6.function.name in ./node_modules/gridsome/app/entry.client.js, ./node_modules/gridsome/app/fetchPath.js and 1 other
* core-js/modules/es6.number.constructor in ./node_modules/gridsome/app/components/Link.js
* core-js/modules/es6.object.define-properties in ./node_modules/gridsome/app/router.js, ./node_modules/gridsome/app/components/Link.js and 2 others
* core-js/modules/es6.object.define-property in ./node_modules/gridsome/app/router.js, ./node_modules/gridsome/app/components/Image.js and 2 others
* core-js/modules/es6.object.keys in ./node_modules/gridsome/app/router.js, ./node_modules/gridsome/app/components/Image.js and 2 others
* core-js/modules/es6.regexp.constructor in ./node_modules/gridsome/app/components/Link.js, ./node_modules/gridsome/app/utils/helpers.js
* core-js/modules/es6.regexp.replace in ./node_modules/gridsome/app/utils/helpers.js, ./node_modules/gridsome/app/utils/class.js
* core-js/modules/es6.regexp.search in ./node_modules/gridsome/app/entry.client.js
* core-js/modules/es6.regexp.split in ./node_modules/gridsome/app/utils/class.js, ./node_modules/gridsome/app/utils/helpers.js
* core-js/modules/es6.string.ends-with in ./node_modules/gridsome/app/directives/image.js
* core-js/modules/es6.string.iterator in ./node_modules/gridsome/app/entry.client.js, ./node_modules/gridsome/app/directives/image.js
* core-js/modules/es6.string.link in ./node_modules/gridsome/app/head.js
* core-js/modules/es6.string.starts-with in ./node_modules/gridsome/app/entry.client.js, ./node_modules/gridsome/app/components/Link.js and 1 other
* core-js/modules/es6.string.trim in ./node_modules/gridsome/app/utils/class.js
* core-js/modules/es6.symbol in ./node_modules/gridsome/app/app.js
* core-js/modules/es7.object.get-own-property-descriptors in ./node_modules/gridsome/app/router.js, ./node_modules/gridsome/app/components/Link.js and 2 others
* core-js/modules/es7.symbol.async-iterator in ./node_modules/gridsome/app/app.js
* core-js/modules/web.dom.iterable in ./node_modules/gridsome/app/entry.client.js, ./node_modules/gridsome/app/app.js and 7 others

To install them, you can run: npm install --save core-js/modules/es6.array.filter core-js/modules/es6.array.for-each core-js/modules/es6.array.from core-js/modules/es6.array.index-of
core-js/modules/es6.array.is-array core-js/modules/es6.array.map core-js/modules/es6.function.name core-js/modules/es6.number.constructor core-js/modules/es6.object.define-properties
core-js/modules/es6.object.define-property core-js/modules/es6.object.keys core-js/modules/es6.regexp.constructor core-js/modules/es6.regexp.replace core-js/modules/es6.regexp.search
core-js/modules/es6.regexp.split core-js/modules/es6.string.ends-with core-js/modules/es6.string.iterator core-js/modules/es6.string.link core-js/modules/es6.string.starts-with core-j
s/modules/es6.string.trim core-js/modules/es6.symbol core-js/modules/es7.object.get-own-property-descriptors core-js/modules/es7.symbol.async-iterator core-js/modules/web.dom.iterable
```

Even though the error is suggesting installing the packages using the command at the end, that doesn't even work:

```
npm ERR! code ENOLOCAL
npm ERR! Could not install from "core-js\modules\es6.array.filter" as it does not contain a package.json file.

npm ERR! A complete log of this run can be found in:
npm ERR!     C:\Users\Denno\AppData\Roaming\npm-cache\_logs\2020-01-03T01_29_05_890Z-debug.log
```