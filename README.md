# Snapkite Engine Stream Client

This helper library handles stream of tweets sent using Socket.IO by [Snapkite Engine](https://github.com/snapkite/snapkite-engine).

## API

```js
var SnapkiteStreamClient = require('../snapkite-stream-client');
```

### `initialiseStream()`

Connects to [Snapkite Engine](https://github.com/snapkite/snapkite-engine) and invokes callback function on receiving new tweet:

```js
SnapkiteStreamClient.initialiseStream(callback, options);
```

Callback function should handle tweet object:

```js
function callback(tweet) {
  // ... handle tweet object
}
```

#### `options` object:

+ `hostname`

Default: `localhost`.

+ `port`

Default: `3000`.

+ `delayInMilliseconds`

Tweets can arrive at a very fast pace, so to prevent that you can set the minimum delay between tweets. Delay is set in milliseconds.

Default: `1500`

+ `cacheNumberOfTweets`

If you set a delay between receiving new tweets, you might want to cache them. Tweets that are not cached will be dropped.

Default: `20`

### `destroyStream()`

Disconnect from [Snapkite Engine](https://github.com/snapkite/snapkite-engine).

```javascript
SnapkiteStreamClient.destroyStream();
```

## License

This library is released under the MIT license.

This software comes with NO WARRANTY, expressed or implied.
