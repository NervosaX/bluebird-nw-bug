Overview
========

This shows a bug in bluebird where JSPM and node webkit stopped working
somewhere between 2.9.14 and 2.9.15. The issue not fixed all the way up
to 2.9.25 at the time of this repo.

## Requirements

* The node webkit binary https://github.com/nwjs/nw.js

* This source code cloned somewhere

## Usage

* Get the nodewebkit (nw) binary for your platform and extract it
* Run the dist folder with the nw binary:


```shell
nw dist
```

## What should happen

The textarea should display that the promise resolved correctly

## What actually happens

The following stack trace is returned:

```
TypeError: Illegal invocation
    at n.2.n._queueTick (https://npm.jspm.io/bluebird@2.9.15/js/browser/bluebird.js:2:2630)
    at n.2.n.invoke (https://npm.jspm.io/bluebird@2.9.15/js/browser/bluebird.js:2:2165)
    at e.23.e.exports.e._then (https://npm.jspm.io/bluebird@2.9.15/js/browser/bluebird.js:4:3618)
    at e.23.e.exports.e.then (https://npm.jspm.io/bluebird@2.9.15/js/browser/bluebird.js:4:1997)
    at file:///home/adam/Programming/js/bluebirdnw/dist/index.html:17:14
    at D (https://jspm.io/es6-module-loader@0.16.5.js:1:7439)
    at I (https://jspm.io/es6-module-loader@0.16.5.js:1:7071)
    at O.7.O.when (https://jspm.io/es6-module-loader@0.16.5.js:1:10745)
    at w.7.w.run (https://jspm.io/es6-module-loader@0.16.5.js:1:9781)
    at e.3.e._drain (https://jspm.io/es6-module-loader@0.16.5.js:1:1740)
    at 3.e.drain (https://jspm.io/es6-module-loader@0.16.5.js:1:1394)
    at process._tickCallback (node.js:375:11)
```
