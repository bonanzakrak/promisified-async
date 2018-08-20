# promise-async
> Adds Promises bindings for async library. Works with callbacks as well.

## Install

```bash
npm install promise-async --save
```

If you want to use in the browser (powered by [Browserify](http://browserify.org/)):

```bash
bower install promise-async --save
```

and later link in your HTML:

```html
<script src="bower_components/promise-async/dist/promise-async.js"></script>
```

## Usage

```js
const async = require('promise-async')

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
