dustjs-onload-context extends dustjs to support `dust.onLoad` callbacks which accept the current rendering context. This
can be useful when it's necessary to resolve templates based on state in the render context.

[![Build Status](https://travis-ci.org/totherik/dustjs-onload-context.png)](https://travis-ci.org/totherik/dustjs-onload-context)

#### Example
```javascript
'use strict';

var dust = require('dustjs-linkedin'),
    contextify = require('dustjs-onload-context');

var undo = contextify();
dust.onLoad = function (name, context, cb) {
    var str;

    // context.get('foo');
    // do stuff ...

    cb(null, str);
};
```

#### Usage
To enable support for the `context` argument, simply require and invoke the exported function (which will decorate
dustjs) and assign a function which accepts three arguments to the `onLoad` dust property. Functions assigned to `onLoad`
which only accept 2 arguments are considered a noop and are treated the same as the original dust `onLoad` API.

```
NDOE: The `dustjs-linkedin` module is required, but is not an explicit dependency of this module.
```