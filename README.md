# api documentation for  [st (v1.2.0)](https://github.com/isaacs/st#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-st.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-st) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-st.svg)](https://travis-ci.org/npmdoc/node-npmdoc-st)
#### A module for serving static files.  Does etags, caching, etc.

[![NPM](https://nodei.co/npm/st.png?downloads=true)](https://www.npmjs.com/package/st)

[![apidoc](https://npmdoc.github.io/node-npmdoc-st/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-st_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-st/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-st/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-st/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Isaac Z. Schlueter",
        "email": "i@izs.me",
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
            "name": "isaacs",
            "email": "i@izs.me"
        },
        {
            "name": "rvagg",
            "email": "rod@vagg.org"
        }
    ],
    "name": "st",
    "optionalDependencies": {
        "graceful-fs": "~4.1.4"
    },
    "readme": "ERROR: No README data found!",
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



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module st](#apidoc.module.st)
1.  [function <span class="apidocSignatureSpan">st.</span>Mount (opt)](#apidoc.element.st.Mount)
1.  object <span class="apidocSignatureSpan">st.</span>Mount.prototype

#### [module st.Mount](#apidoc.module.st.Mount)
1.  [function <span class="apidocSignatureSpan">st.</span>Mount (opt)](#apidoc.element.st.Mount.Mount)

#### [module st.Mount.prototype](#apidoc.module.st.Mount.prototype)
1.  [function <span class="apidocSignatureSpan">st.Mount.prototype.</span>_loadContent ()](#apidoc.element.st.Mount.prototype._loadContent)
1.  [function <span class="apidocSignatureSpan">st.Mount.prototype.</span>_loadIndex (p, cb)](#apidoc.element.st.Mount.prototype._loadIndex)
1.  [function <span class="apidocSignatureSpan">st.Mount.prototype.</span>_loadReaddir (p, cb)](#apidoc.element.st.Mount.prototype._loadReaddir)
1.  [function <span class="apidocSignatureSpan">st.Mount.prototype.</span>_loadStat (key, cb)](#apidoc.element.st.Mount.prototype._loadStat)
1.  [function <span class="apidocSignatureSpan">st.Mount.prototype.</span>autoindex (p, req, res)](#apidoc.element.st.Mount.prototype.autoindex)
1.  [function <span class="apidocSignatureSpan">st.Mount.prototype.</span>cachedFile (p, stat, etag, req, res)](#apidoc.element.st.Mount.prototype.cachedFile)
1.  [function <span class="apidocSignatureSpan">st.Mount.prototype.</span>error (er, res)](#apidoc.element.st.Mount.prototype.error)
1.  [function <span class="apidocSignatureSpan">st.Mount.prototype.</span>file (p, fd, stat, etag, req, res, end)](#apidoc.element.st.Mount.prototype.file)
1.  [function <span class="apidocSignatureSpan">st.Mount.prototype.</span>getCacheOptions (opt)](#apidoc.element.st.Mount.prototype.getCacheOptions)
1.  [function <span class="apidocSignatureSpan">st.Mount.prototype.</span>getPath (u)](#apidoc.element.st.Mount.prototype.getPath)
1.  [function <span class="apidocSignatureSpan">st.Mount.prototype.</span>getUrl (p)](#apidoc.element.st.Mount.prototype.getUrl)
1.  [function <span class="apidocSignatureSpan">st.Mount.prototype.</span>index (p, req, res)](#apidoc.element.st.Mount.prototype.index)
1.  [function <span class="apidocSignatureSpan">st.Mount.prototype.</span>serve (req, res, next)](#apidoc.element.st.Mount.prototype.serve)
1.  [function <span class="apidocSignatureSpan">st.Mount.prototype.</span>streamFile (p, fd, stat, etag, req, res, end)](#apidoc.element.st.Mount.prototype.streamFile)



# <a name="apidoc.module.st"></a>[module st](#apidoc.module.st)

#### <a name="apidoc.element.st.Mount"></a>[function <span class="apidocSignatureSpan">st.</span>Mount (opt)](#apidoc.element.st.Mount)
- description and source-code
```javascript
function Mount(opt) {
  if (!opt) throw new Error('no options provided')
  if (typeof opt !== 'object') throw new Error('invalid options')
  if (!(this instanceof Mount)) return new Mount(opt)

  this.opt = opt
  this.url = opt.url
  this.path = opt.path
  this._index = opt.index === false ? false
              : typeof opt.index === 'string' ? opt.index
              : true
  this.fdman = FD()

  // cache basically everything
  var c = this.getCacheOptions(opt)
  this.cache = {
    fd: AC(c.fd),
    stat: AC(c.stat),
    index: AC(c.index),
    readdir: AC(c.readdir),
    content: AC(c.content)
  }

  this._cacheControl =
    c.content.maxAge === false
      ? undefined
      : typeof c.content.cacheControl == 'string'
        ? c.content.cacheControl
        : opt.cache === false
          ? 'no-cache'
          : 'public, max-age=' + (c.content.maxAge / 1000)
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.st.Mount"></a>[module st.Mount](#apidoc.module.st.Mount)

#### <a name="apidoc.element.st.Mount.Mount"></a>[function <span class="apidocSignatureSpan">st.</span>Mount (opt)](#apidoc.element.st.Mount.Mount)
- description and source-code
```javascript
function Mount(opt) {
  if (!opt) throw new Error('no options provided')
  if (typeof opt !== 'object') throw new Error('invalid options')
  if (!(this instanceof Mount)) return new Mount(opt)

  this.opt = opt
  this.url = opt.url
  this.path = opt.path
  this._index = opt.index === false ? false
              : typeof opt.index === 'string' ? opt.index
              : true
  this.fdman = FD()

  // cache basically everything
  var c = this.getCacheOptions(opt)
  this.cache = {
    fd: AC(c.fd),
    stat: AC(c.stat),
    index: AC(c.index),
    readdir: AC(c.readdir),
    content: AC(c.content)
  }

  this._cacheControl =
    c.content.maxAge === false
      ? undefined
      : typeof c.content.cacheControl == 'string'
        ? c.content.cacheControl
        : opt.cache === false
          ? 'no-cache'
          : 'public, max-age=' + (c.content.maxAge / 1000)
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.st.Mount.prototype"></a>[module st.Mount.prototype](#apidoc.module.st.Mount.prototype)

#### <a name="apidoc.element.st.Mount.prototype._loadContent"></a>[function <span class="apidocSignatureSpan">st.Mount.prototype.</span>_loadContent ()](#apidoc.element.st.Mount.prototype._loadContent)
- description and source-code
```javascript
_loadContent = function () {
  // this function should never be called.
  // we check if the thing is in the cache, and if not, stream it in
  // manually.  this.cache.content.get() should not ever happen.
  throw new Error('This should not ever happen')
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.st.Mount.prototype._loadIndex"></a>[function <span class="apidocSignatureSpan">st.Mount.prototype.</span>_loadIndex (p, cb)](#apidoc.element.st.Mount.prototype._loadIndex)
- description and source-code
```javascript
_loadIndex = function (p, cb) {
  // truncate off the first bits
  var url = p.substr(this.path.length).replace(/\\/g, '/')
  var t = url
      .replace(/"/g, '&quot;')
      .replace(/</g, '&lt;')
      .replace(/>/g, '&gt;')
      .replace(/'/g, '&#39;')

  var str =
    '<!doctype html>' +
    '<html>' +
    '<head><title>Index of ' + t + '</title></head>' +
    '<body>' +
    '<h1>Index of ' + t + '</h1>' +
    '<hr><pre><a href="../">../</a>\n'

  this.cache.readdir.get(p, function (er, data) {
    if (er) return cb(er)

    var nameLen = 0
    var sizeLen = 0

    Object.keys(data).map(function (f) {
      var d = data[f]

      var name = f
          .replace(/"/g, '&quot;')
          .replace(/</g, '&lt;')
          .replace(/>/g, '&gt;')
          .replace(/'/g, '&#39;')

      if (d.size === '-') name += '/'
      var showName = name.replace(/^(.{40}).{3,}$/, '$1..>')
      var linkName = encodeURIComponent(name)
                     .replace(/%2e/ig, '.')     // Encoded dots are dots
                     .replace(/%2f|%5c/ig, '/') // encoded slashes are /
                     .replace(/[\/\\]/g, '/')   // back slashes are slashes

      nameLen = Math.max(nameLen, showName.length)
      sizeLen = Math.max(sizeLen, ('' + d.size).length)
      return [ '<a href="' + linkName + '">' + showName + '</a>',
               d.mtime, d.size, showName ]
    }).sort(function (a, b) {
      return a[2] === '-' && b[2] !== '-' ? -1 // dirs first
           : a[2] !== '-' && b[2] === '-' ? 1
           : a[0].toLowerCase() < b[0].toLowerCase() ? -1 // then alpha
           : a[0].toLowerCase() > b[0].toLowerCase() ? 1
           : 0
    }).forEach(function (line) {
      var namePad = new Array(8 + nameLen - line[3].length).join(' ')
      var sizePad = new Array(8 + sizeLen - ('' + line[2]).length).join(' ')
      str += line[0] + namePad +
             line[1].toISOString() +
             sizePad + line[2] + '\n'
    })

    str += '</pre><hr></body></html>'
    cb(null, new Buffer(str))
  })
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.st.Mount.prototype._loadReaddir"></a>[function <span class="apidocSignatureSpan">st.Mount.prototype.</span>_loadReaddir (p, cb)](#apidoc.element.st.Mount.prototype._loadReaddir)
- description and source-code
```javascript
_loadReaddir = function (p, cb) {
  var len
  var data
  fs.readdir(p, function (er, files) {
    if (er) return cb(er)
    files = files.filter(function (f) {
      if (!this.opt.dot) return !/^\./.test(f)
      else return f !== '.' && f !== '..'
    }.bind(this))
    len = files.length
    data = {}
    files.forEach(function (file) {
      var pf = path.join(p, file)
      this.cache.stat.get(pf, function (er, stat) {
        if (er) return cb(er)
        if (stat.isDirectory()) stat.size = '-'
        data[file] = stat
        next()
      }.bind(this))
    }.bind(this))
  }.bind(this))

  function next () {
    if (--len === 0) cb(null, data)
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.st.Mount.prototype._loadStat"></a>[function <span class="apidocSignatureSpan">st.Mount.prototype.</span>_loadStat (key, cb)](#apidoc.element.st.Mount.prototype._loadStat)
- description and source-code
```javascript
_loadStat = function (key, cb) {
  // key is either fd:path or just a path
  var fdp = key.match(/^(\d+):(.*)/)
  if (fdp) {
    var fd = +fdp[1]
    var p = fdp[2]
    fs.fstat(fd, function (er, stat) {
      if (er) return cb(er)
      this.cache.stat.set(p, stat)
      cb(null, stat)
    }.bind(this))
  } else {
    fs.stat(key, cb)
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.st.Mount.prototype.autoindex"></a>[function <span class="apidocSignatureSpan">st.Mount.prototype.</span>autoindex (p, req, res)](#apidoc.element.st.Mount.prototype.autoindex)
- description and source-code
```javascript
autoindex = function (p, req, res) {
  if (!/\/$/.exec(req.sturl)) {
    res.statusCode = 301
    res.setHeader('location', req.sturl + '/')
    res.end('Moved: ' + req.sturl + '/')
    return
  }

  this.cache.index.get(p, function (er, html) {
    if (er) return this.error(er, res)

    res.statusCode = 200
    res.setHeader('content-type', 'text/html')
    res.setHeader('content-length', html.length)
    res.end(html)
  }.bind(this))
}
```
- example usage
```shell
...

res.setHeader('content-type', 'text/plain')
res.end(http.STATUS_CODES[res.statusCode] + '\n')
}

Mount.prototype.index = function (p, req, res) {
if (this._index === true) {
  return this.autoindex(p, req, res)
}
if (typeof this._index === 'string') {
  if (!/\/$/.test(req.sturl)) req.sturl += '/'
  req.sturl += this._index
  return this.serve(req, res)
}
return this.error(404, res)
...
```

#### <a name="apidoc.element.st.Mount.prototype.cachedFile"></a>[function <span class="apidocSignatureSpan">st.Mount.prototype.</span>cachedFile (p, stat, etag, req, res)](#apidoc.element.st.Mount.prototype.cachedFile)
- description and source-code
```javascript
cachedFile = function (p, stat, etag, req, res) {
  var key = stat.size + ':' + etag
  var gz = this.opt.gzip !== false && getGz(p, req)

  this.cache.content.get(key, function (er, content) {
    if (er) return this.error(er, res)
    res.statusCode = 200
    if (this.opt.cachedHeader)
      res.setHeader('x-from-cache', 'true')
    if (gz && content.gz) {
      res.setHeader('content-encoding', 'gzip')
      res.setHeader('content-length', content.gz.length)
      res.end(content.gz)
    } else {
      res.setHeader('content-length', content.length)
      res.end(content)
    }
  }.bind(this))
}
```
- example usage
```shell
...
if (mt !== 'application/octet-stream') {
  res.setHeader('content-type', mt)
}

// only use the content cache if it will actually fit there.
if (this.cache.content.has(key)) {
  end()
  this.cachedFile(p, stat, etag, req, res)
} else {
  this.streamFile(p, fd, stat, etag, req, res, end)
}
}

Mount.prototype.cachedFile = function (p, stat, etag, req, res) {
var key = stat.size + ':' + etag
...
```

#### <a name="apidoc.element.st.Mount.prototype.error"></a>[function <span class="apidocSignatureSpan">st.Mount.prototype.</span>error (er, res)](#apidoc.element.st.Mount.prototype.error)
- description and source-code
```javascript
error = function (er, res) {
  res.statusCode = typeof er === 'number' ? er
                 : er.code === 'ENOENT' || er.code === 'EISDIR' ? 404
                 : er.code === 'EPERM' || er.code === 'EACCES' ? 403
                 : 500

  if (typeof res.error === 'function') {
    // pattern of express and ErrorPage
    return res.error(res.statusCode, er)
  }

  res.setHeader('content-type', 'text/plain')
  res.end(http.STATUS_CODES[res.statusCode] + '\n')
}
```
- example usage
```shell
...
// inability to open is some kind of error, probably 404
// if we're in passthrough, AND got a next function, we can
// fall through to that.  otherwise, we already returned true,
// send an error.
if (er) {
  if (this.opt.passthrough === true && er.code === 'ENOENT' && next)
    return next()
  return this.error(er, res)
}

// we may be about to use this, so don't let it be closed by cache purge
this.fdman.checkout(p, fd)
// a safe end() function that can be called multiple times but
// only perform a single checkin
var end = this.fdman.checkinfn(p, fd)
...
```

#### <a name="apidoc.element.st.Mount.prototype.file"></a>[function <span class="apidocSignatureSpan">st.Mount.prototype.</span>file (p, fd, stat, etag, req, res, end)](#apidoc.element.st.Mount.prototype.file)
- description and source-code
```javascript
file = function (p, fd, stat, etag, req, res, end) {
  var key = stat.size + ':' + etag

  var mt = mime.lookup(path.extname(p))
  if (mt !== 'application/octet-stream') {
    res.setHeader('content-type', mt)
  }

  // only use the content cache if it will actually fit there.
  if (this.cache.content.has(key)) {
    end()
    this.cachedFile(p, stat, etag, req, res)
  } else {
    this.streamFile(p, fd, stat, etag, req, res, end)
  }
}
```
- example usage
```shell
...
        res.setHeader('Access-Control-Allow-Origin', '*')
        res.setHeader('Access-Control-Allow-Headers',
          'Origin, X-Requested-With, Content-Type, Accept, Range')
      }

      return isDirectory
        ? this.index(p, req, res)
        : this.file(p, fd, stat, etag, req, res, end)
    }.bind(this))
  }.bind(this))

  return true
}

Mount.prototype.error = function (er, res) {
...
```

#### <a name="apidoc.element.st.Mount.prototype.getCacheOptions"></a>[function <span class="apidocSignatureSpan">st.Mount.prototype.</span>getCacheOptions (opt)](#apidoc.element.st.Mount.prototype.getCacheOptions)
- description and source-code
```javascript
getCacheOptions = function (opt) {
  var o = opt.cache
    , set = function (key) {
        return o[key] === false
          ? util._extend({}, none)
          : util._extend(util._extend({}, d[key]), o[key])
      }

  if (o === false)
    o = noCaching
  else if (!o)
    o = {}

  var d = defaultCacheOptions

  // should really only ever set max and maxAge here.
  // load and fd disposal is important to control.
  var c = {
    fd: set('fd'),
    stat: set('stat'),
    index: set('index'),
    readdir: set('readdir'),
    content: set('content'),
  }

  c.fd.dispose = this.fdman.close.bind(this.fdman)
  c.fd.load = this.fdman.open.bind(this.fdman)

  c.stat.load = this._loadStat.bind(this)
  c.index.load = this._loadIndex.bind(this)
  c.readdir.load = this._loadReaddir.bind(this)
  c.content.load = this._loadContent.bind(this)
  return c
}
```
- example usage
```shell
...
this.path = opt.path
this._index = opt.index === false ? false
            : typeof opt.index === 'string' ? opt.index
            : true
this.fdman = FD()

// cache basically everything
var c = this.getCacheOptions(opt)
this.cache = {
  fd: AC(c.fd),
  stat: AC(c.stat),
  index: AC(c.index),
  readdir: AC(c.readdir),
  content: AC(c.content)
}
...
```

#### <a name="apidoc.element.st.Mount.prototype.getPath"></a>[function <span class="apidocSignatureSpan">st.Mount.prototype.</span>getPath (u)](#apidoc.element.st.Mount.prototype.getPath)
- description and source-code
```javascript
getPath = function (u) {
  var p = url.parse(u).pathname

  // Encoded dots are dots
  p = p.replace(/%2e/ig, '.')

  // encoded slashes are /
  p = p.replace(/%2f|%5c/ig, '/')

  // back slashes are slashes
  p = p.replace(/[\/\\]/g, '/')

  // Make sure it starts with a slash
  p = p.replace(/^\//, '/')

  if (p.match(/[\/\\]\.\.[\/\\]/)) {
    // traversal urls not ever even slightly allowed. clearly shenanigans
    // send a 403 on that noise, do not pass go, do not collect $200
    return 403
  }

  u = path.normalize(p).replace(/\\/g, '/')
  if (u.indexOf(this.url) !== 0) return false

  try {
    u = decodeURIComponent(u)
  }
  catch (e) {
    // if decodeURIComponent failed, we weren't given a valid URL to begin with.
    return false
  }

  // /a/b/c mounted on /path/to/z/d/x
  // /a/b/c/d --> /path/to/z/d/x/d
  u = u.substr(this.url.length)
  if (u.charAt(0) !== '/') u = '/' + u

  p = path.join(this.path, u)
  return p
}
```
- example usage
```shell
...
  return false
}

// querystrings are of no concern to us
if (!req.sturl)
  req.sturl = url.parse(req.url).pathname

var p = this.getPath(req.sturl)

// Falsey here means we got some kind of invalid path.
// Probably urlencoding we couldn't understand, or some
// other "not compatible with st, but maybe ok" thing.
if (!p) {
  if (typeof next === 'function') next()
  return false
...
```

#### <a name="apidoc.element.st.Mount.prototype.getUrl"></a>[function <span class="apidocSignatureSpan">st.Mount.prototype.</span>getUrl (p)](#apidoc.element.st.Mount.prototype.getUrl)
- description and source-code
```javascript
getUrl = function (p) {
  p = path.resolve(p)
  if (p.indexOf(this.path) !== 0) return false
  p = path.join('/', p.substr(this.path.length))
  var u = path.join(this.url, p).replace(/\\/g, '/')
  return u
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.st.Mount.prototype.index"></a>[function <span class="apidocSignatureSpan">st.Mount.prototype.</span>index (p, req, res)](#apidoc.element.st.Mount.prototype.index)
- description and source-code
```javascript
index = function (p, req, res) {
  if (this._index === true) {
    return this.autoindex(p, req, res)
  }
  if (typeof this._index === 'string') {
    if (!/\/$/.test(req.sturl)) req.sturl += '/'
    req.sturl += this._index
    return this.serve(req, res)
  }
  return this.error(404, res)
}
```
- example usage
```shell
...
      if (this.opt.cors) {
        res.setHeader('Access-Control-Allow-Origin', '*')
        res.setHeader('Access-Control-Allow-Headers',
          'Origin, X-Requested-With, Content-Type, Accept, Range')
      }

      return isDirectory
        ? this.index(p, req, res)
        : this.file(p, fd, stat, etag, req, res, end)
    }.bind(this))
  }.bind(this))

  return true
}
...
```

#### <a name="apidoc.element.st.Mount.prototype.serve"></a>[function <span class="apidocSignatureSpan">st.Mount.prototype.</span>serve (req, res, next)](#apidoc.element.st.Mount.prototype.serve)
- description and source-code
```javascript
serve = function (req, res, next) {
  if (req.method !== 'HEAD' && req.method !== 'GET') {
    if (typeof next === 'function') next()
    return false
  }

  // querystrings are of no concern to us
  if (!req.sturl)
    req.sturl = url.parse(req.url).pathname

  var p = this.getPath(req.sturl)

  // Falsey here means we got some kind of invalid path.
  // Probably urlencoding we couldn't understand, or some
  // other "not compatible with st, but maybe ok" thing.
  if (!p) {
    if (typeof next === 'function') next()
    return false
  }

  // don't allow dot-urls by default, unless explicitly allowed.
  // If we got a 403, then it's explicitly forbidden.
  if (p === 403 || !this.opt.dot && req.sturl.match(/(^|\/)\./)) {
    res.statusCode = 403
    res.end('Forbidden')
    return true
  }

  // now we have a path.  check for the fd.
  this.cache.fd.get(p, function (er, fd) {
    // inability to open is some kind of error, probably 404
    // if we're in passthrough, AND got a next function, we can
    // fall through to that.  otherwise, we already returned true,
    // send an error.
    if (er) {
      if (this.opt.passthrough === true && er.code === 'ENOENT' && next)
        return next()
      return this.error(er, res)
    }

    // we may be about to use this, so don't let it be closed by cache purge
    this.fdman.checkout(p, fd)
    // a safe end() function that can be called multiple times but
    // only perform a single checkin
    var end = this.fdman.checkinfn(p, fd)

    this.cache.stat.get(fd+':'+p, function (er, stat) {
      if (er) {
        if (next && this.opt.passthrough === true && this._index === false) {
          return next()
        }
        end()
        return this.error(er, res)
      }

      var isDirectory = stat.isDirectory()

      if (isDirectory) {
        end() // we won't need this fd for a directory in any case
        if (next && this.opt.passthrough === true && this._index === false) {
          // this is done before if-modified-since and if-non-match checks so
          // cached modified and etag values won't return 304's if we've since
          // switched to !index. See Issue #51.
          return next()
        }
      }

      var ims = req.headers['if-modified-since']
      if (ims) ims = new Date(ims).getTime()
      if (ims && ims >= stat.mtime.getTime()) {
        res.statusCode = 304
        res.end()
        return end()
      }

      var etag = getEtag(stat)
      if (req.headers['if-none-match'] === etag) {
        res.statusCode = 304
        res.end()
        return end()
      }

      // only set headers once we're sure we'll be serving this request
      if (!res.getHeader('cache-control') && this._cacheControl)
        res.setHeader('cache-control', this._cacheControl)
      res.setHeader('last-modified', stat.mtime.toUTCString())
      res.setHeader('etag', etag)

      if (this.opt.cors) {
        res.setHeader('Access-Control-Allow-Origin', '*')
        res.setHeader('Access-Control-Allow-Headers',
          'Origin, X-Requested-With, Content-Type, Accept, Range')
      }

      return isDirectory
        ? this.index(p, req, res)
        : this.file(p, fd, stat, etag, req, res, end)
    }.bind(this))
  }.bind(this))

  return true
}
```
- example usage
```shell
...
Mount.prototype.index = function (p, req, res) {
if (this._index === true) {
  return this.autoindex(p, req, res)
}
if (typeof this._index === 'string') {
  if (!/\/$/.test(req.sturl)) req.sturl += '/'
  req.sturl += this._index
  return this.serve(req, res)
}
return this.error(404, res)
}

Mount.prototype.autoindex = function (p, req, res) {
if (!/\/$/.exec(req.sturl)) {
  res.statusCode = 301
...
```

#### <a name="apidoc.element.st.Mount.prototype.streamFile"></a>[function <span class="apidocSignatureSpan">st.Mount.prototype.</span>streamFile (p, fd, stat, etag, req, res, end)](#apidoc.element.st.Mount.prototype.streamFile)
- description and source-code
```javascript
streamFile = function (p, fd, stat, etag, req, res, end) {
  var streamOpt = { fd: fd, start: 0, end: stat.size }
  var stream = fs.createReadStream(p, streamOpt)
  stream.destroy = function () {}

  // gzip only if not explicitly turned off or client doesn't accept it
  var gzOpt = this.opt.gzip !== false
  var gz = gzOpt && getGz(p, req)
  var cachable = this.cache.content._cache.max > stat.size
  var gzstr

  // need a gzipped version for the cache, so do it regardless of what the client wants
  if (gz || (gzOpt && cachable)) gzstr = zlib.Gzip()

  // too late to effectively handle any errors.
  // just kill the connection if that happens.
  stream.on('error', function(e) {
    console.error('Error serving %s fd=%d\n%s', p, fd, e.stack || e.message)
    res.socket.destroy()
    end()
  })

  if (res.filter) stream = stream.pipe(res.filter)

  res.statusCode = 200

  if (gz) {
    // we don't know how long it'll be, since it will be compressed.
    res.setHeader('content-encoding', 'gzip')
    stream.pipe(gzstr).pipe(res)
  } else {
    if (!res.filter) res.setHeader('content-length', stat.size)
    stream.pipe(res)
    if (gzstr)
      stream.pipe(gzstr) // for cache
  }

  stream.on('end', function () {
    process.nextTick(end)
  })

  if (cachable) {
    // collect it, and put it in the cache

    var calls = 0

    // called by bl() for both the raw stream and gzipped stream if we're
    // caching gzipped data
    var collectEnd = function () {
      if (++calls == (gzOpt ? 2 : 1)) {
        var content = bufs.slice()
        content.gz = gzbufs && gzbufs.slice()
        this.cache.content.set(key, content)
      }
    }.bind(this)

    var key = stat.size + ':' + etag
    var bufs = bl(collectEnd)
    var gzbufs

    stream.pipe(bufs)

    if (gzstr) {
      gzbufs = bl(collectEnd)
      gzstr.pipe(gzbufs)
    }
  }
}
```
- example usage
```shell
...
}

// only use the content cache if it will actually fit there.
if (this.cache.content.has(key)) {
  end()
  this.cachedFile(p, stat, etag, req, res)
} else {
  this.streamFile(p, fd, stat, etag, req, res, end)
}
}

Mount.prototype.cachedFile = function (p, stat, etag, req, res) {
var key = stat.size + ':' + etag
var gz = this.opt.gzip !== false && getGz(p, req)
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
