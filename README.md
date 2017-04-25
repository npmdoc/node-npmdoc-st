# npmdoc-st

#### basic api documentation for  [st (v1.2.0)](https://github.com/isaacs/st#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-st.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-st) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-st.svg)](https://travis-ci.org/npmdoc/node-npmdoc-st)

#### A module for serving static files.  Does etags, caching, etc.

[![NPM](https://nodei.co/npm/st.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/st)

- [https://npmdoc.github.io/node-npmdoc-st/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-st/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-st/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-st/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-st/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-st/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Isaac Z. Schlueter",
        "url": "http://blog.izs.me/"
    },
    "bin": {
        "st": "bin/server.js"
    },
    "bugs": {
        "url": "https://github.com/isaacs/st/issues"
    },
    "dependencies": {
        "async-cache": "~1.1.0",
        "bl": "~1.1.2",
        "fd": "~0.0.2",
        "graceful-fs": "~4.1.4",
        "mime": "~1.3.4",
        "negotiator": "~0.6.1"
    },
    "description": "A module for serving static files.  Does etags, caching, etc.",
    "devDependencies": {
        "request": "~2.72.0",
        "rimraf": "~2.5.2",
        "tap": "~5.8.0"
    },
    "directories": {},
    "dist": {
        "shasum": "e6313c1836a0889e8507be5bb189b2245266c2df",
        "tarball": "https://registry.npmjs.org/st/-/st-1.2.0.tgz"
    },
    "gitHead": "2a5f970083ee44a03c3cbcb21a12d0ac90230200",
    "homepage": "https://github.com/isaacs/st#readme",
    "keywords": [
        "static",
        "file",
        "serve",
        "etag",
        "autoindex",
        "cache"
    ],
    "license": "ISC",
    "main": "st.js",
    "maintainers": [
        {
            "name": "isaacs"
        },
        {
            "name": "rvagg"
        }
    ],
    "name": "st",
    "optionalDependencies": {
        "graceful-fs": "~4.1.4"
    },
    "repository": {
        "type": "git",
        "url": "git://github.com/isaacs/st.git"
    },
    "scripts": {
        "test": "tap test/*.js test/cli/*-test.js"
    },
    "version": "1.2.0"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
