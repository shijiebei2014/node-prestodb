# Presto db Client

A new wrapper around [Presto HTTP API](https://github.com/prestodb/presto/wiki/HTTP-Protocol) wrapper for Node.js.

Keep consistent with the https://www.npmjs.com/package/prestodb(@0.2.0) and the https://github.com/lourenzo/node-prestodb(@0.2.0)
## Usage

```js
'use strict';

const PrestoClient = require('prestodb');

let prestoClient = new PrestoClient({
  url: 'http://server-url:8080',
  user: 'presto',
  catalog: 'catalog',
  schema: 'schema',
  nextUriTimeout: 200 // in miliseconds
});

prestoClient.sendStatement('SELECT * FROM catalog.schema.table')
  .then((result) => {
    console.log(result)
  })
  .catch((error) => {
    console.error({ error })
  });
```


## Todo

- [ ] Offer a EventEmitter version
- [ ] Send progress info
- [ ] More efficient request queueing and throttling 
