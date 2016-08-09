# JSON Fetch

A wrapper around ES6 fetch to simplify interacting with JSON APIs.

- resolve with json for 200-level responses
- reject with an error for non 200-level responses
- retry request for network errors
- automatically JSON stringify request body
- set JSON request headers
- include request credentials

[![build status][travis-badge]][travis-link]
[![npm version][npm-badge]][npm-link]
[![MIT license][license-badge]][license-link]
[![we're hiring][hiring-badge]][hiring-link]

## Usage

```
npm install json-fetch
```

```js
import es6Promise from 'es6-promise'
es6Promise.polyfill()
import jsonFetch from 'json-fetch'

jsonFetch('http://www.test.com/products/1234', {
  method: 'POST',
  body: {name: 'apple'},
  credentials: 'omit', // "include" by default, be careful!
}).then(response => {
  // handle 200-level responses:
  console.log(response.body) // json response here
  console.log(response.status)
  console.log(response.statusText)
  console.log(response.headers)
}).catch(err => {
  // handle non 200-level responses:
  console.log(err.message)
  console.log(err.body)
  console.log(err.status)
  console.log(err.statusText)
  console.log(err.headers)
})
```

## Contributing

Please follow our [Code of Conduct](https://github.com/goodeggs/json-fetch/blob/master/CODE_OF_CONDUCT.md)
when contributing to this project.

```
$ git clone https://github.com/goodeggs/json-fetch && cd json-fetch
$ npm install
$ npm test
```

_Module scaffold generated by [generator-goodeggs-npm](https://github.com/goodeggs/generator-goodeggs-npm)._


[travis-badge]: http://img.shields.io/travis/goodeggs/json-fetch.svg?style=flat-square
[travis-link]: https://travis-ci.org/goodeggs/json-fetch
[npm-badge]: http://img.shields.io/npm/v/json-fetch.svg?style=flat-square
[npm-link]: https://www.npmjs.org/package/json-fetch
[license-badge]: http://img.shields.io/badge/license-MIT-blue.svg?style=flat-square
[license-link]: LICENSE.md
[hiring-badge]: https://img.shields.io/badge/we're_hiring-yes-brightgreen.svg?style=flat-square
[hiring-link]: http://goodeggs.jobscore.com/?detail=Open+Source&sid=161
