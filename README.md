# promisified-async
> Adds Promises bindings for async library. Works with callbacks as well.

## Install

```bash
npm install promisified-async --save
```

## Usage

```js
const async = require('promisified-async')

async.waterfall([
  function (callback) {
    callback(null, 'one', 'two')
  },
  function (arg1, arg2, callback) {
    // arg1 now equals 'one' and arg2 now equals 'two'
    callback(null, 'three')
  },
  function (arg1, callback) {
    // arg1 now equals 'three'
    callback(null, 'done')
  }
]).then(function (value) {
  console.log(value === 'done') // => true
})
```

## License

MIT © Bonanza
