# is-es2015

This module exports, as ESM or CJS, just the following:

```js
/^class\b/.test(class{})
```

The goal of this module is to understand if the current environment is running transpiled code or not.

> ... and why is that relevant?

Because transpiled code can be untrusted due various transpilers out there, meaning some expected feature such as native classes extends, species, etc, might not work as expected.

If this module returns `true`, your code targets at least ES2015, but if it returns `false`, your code is likely running to target IE11 or lower.

```js
import isES2015 from 'is-es2015';

export default isES2015 ?
  class Celebrate {} :
  function PoorThing() {}
;
```
