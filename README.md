
WHATWG `fetch` API for ALL JavaScript environments.  Built on top of [isomorphic-fetch](https://github.com/matthew-andrews/isomorphic-fetch) & [GitHub's WHATWG Fetch polyfill](https://github.com/github/fetch).

The idea behind this npm module is to support ALL JavaScript environments. If doesn't work for you, open a issue and we will support it.

:)

## Suported environments

- node.js
- browser
- browserify
- webpack
- react-native

## Warnings

- This adds `fetch` as a global so that its API is consistent between client and server.
- You must bring your own ES6 Promise compatible polyfill, I suggest [es6-promise](https://github.com/jakearchibald/es6-promise).

## Installation

### NPM

```sh
npm install --save fetch-everywhere es6-promise
```

### Bower

```sh
bower install --save fetch-everywhere es6-promise
```

## Usage

```js
require('es6-promise').polyfill();
require('fetch-everywhere');

fetch('//offline-news-api.herokuapp.com/stories')
	.then(function(response) {
		if (response.status >= 400) {
			throw new Error("Bad response from server");
		}
		return response.json();
	})
	.then(function(stories) {
		console.log(stories);
	});
```

## License
Thanks to
