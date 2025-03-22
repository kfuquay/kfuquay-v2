---
title: Notable New Node Features
slug: notable-new-node-features
description: Quick notes on features added to Node.js in versions 18, 20, and 22.
publishDate: 4 June 2024
---

The video <a href="https://www.youtube.com/watch?v=evCnOaVaOTo" target="_blank">"Node.js and its many, many new features with Matteo Collina"</a> has piqued my interest and encouraged me to explore the recent additions to Node.js that I hadn't known about before.

## [Test Runner](https://nodejs.org/api/test.html)

Import the test module into test files:

```js
import test from 'node:test';
```

Run test:

```shellscript
node --test foo.js
```

This feature was introduced version 18 and became stable in version 20.

### [Code Coverage](https://nodejs.org/api/test.html#collecting-code-coverage)

The `--experimental-test-coverage` command line flag was introduced in version 20 and is still considered experimental as of version 22.

For code coverage, you can also utilize [`c8`](https://github.com/bcoe/c8). 

Install it using

```shellscript
npm i c8
```

Run it via

```shellscript
npx c8 node foo.js.
```

## [--watch](https://nodejs.org/docs/v20.13.1/api/cli.html#--watch)

Introduced in v18 and stable in v20. Can be used in conjunction with node's test runner. (So long, [nodemon](https://www.npmjs.com/package/nodemon)).

```shellscript
node --watch --test foo.js
```

## [Compile Cache](https://nodejs.org/en/blog/release/v22.1.0#module-implement-node_compile_cache-for-automatic-on-disk-code-caching)

Introduced in v22.1 (unstable).

Speeds up compilation by using "on-disk [V8 code cache](https://v8.dev/blog/code-caching-for-devs) persisted in the specified directory".

Enable by setting environment variable 

```dotenv
NODE_COMPILE_CACHE=/path/to/cache/dir
```

Note important caveat in the blog post: "currently when using this with V8 JavaScript code coverage, the coverage being collected by V8 may be less precise in functions that are deserialized from the code cache. It's recommended to turn this off when running tests to generate precise coverage."