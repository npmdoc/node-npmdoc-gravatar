# api documentation for  [gravatar (v1.6.0)](https://github.com/emerleite/node-gravatar#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-gravatar.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gravatar) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gravatar.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gravatar)
#### Gravatar Node.js library

[![NPM](https://nodei.co/npm/gravatar.png?downloads=true)](https://www.npmjs.com/package/gravatar)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gravatar/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-gravatar_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gravatar/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-gravatar/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-gravatar/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Emerson Macedo",
        "email": "emerleite@gmail.com"
    },
    "bin": {
        "gravatar": "cli.js"
    },
    "bugs": {
        "url": "https://github.com/emerleite/node-gravatar/issues"
    },
    "dependencies": {
        "blueimp-md5": "^2.3.0",
        "email-validator": "^1.0.7",
        "querystring": "0.2.0",
        "yargs": "^6.0.0"
    },
    "description": "Gravatar Node.js library",
    "devDependencies": {
        "mocha": "1.21.4",
        "nixt": "^0.4.1",
        "should": "4.0.4"
    },
    "directories": {},
    "dist": {
        "shasum": "8bdc9b786ca725a8e7076416d1731f8d3331c976",
        "tarball": "https://registry.npmjs.org/gravatar/-/gravatar-1.6.0.tgz"
    },
    "engines": {
        "node": ">=0.8.0"
    },
    "gitHead": "f77fba222b7d531af695bf11dda21f44d4f0fd8e",
    "homepage": "https://github.com/emerleite/node-gravatar#readme",
    "keywords": [
        "gravatar",
        "avatar",
        "package.json"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "emerleite",
            "email": "emerleite@gmail.com"
        }
    ],
    "name": "gravatar",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/emerleite/node-gravatar.git"
    },
    "scripts": {
        "test": "node_modules/mocha/bin/mocha -R spec"
    },
    "version": "1.6.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module gravatar](#apidoc.module.gravatar)
1.  [function <span class="apidocSignatureSpan">gravatar.</span>profile_url (email, options, https)](#apidoc.element.gravatar.profile_url)
1.  [function <span class="apidocSignatureSpan">gravatar.</span>url (email, options, protocol)](#apidoc.element.gravatar.url)



# <a name="apidoc.module.gravatar"></a>[module gravatar](#apidoc.module.gravatar)

#### <a name="apidoc.element.gravatar.profile_url"></a>[function <span class="apidocSignatureSpan">gravatar.</span>profile_url (email, options, https)](#apidoc.element.gravatar.profile_url)
- description and source-code
```javascript
profile_url = function (email, options, https) {
  var format = options != undefined && options.format != undefined ?  String(options.format) : 'json'
  if (options && options.protocol) https = proto(options);
  var baseURL = (https && "https://secure.gravatar.com/") || 'http://www.gravatar.com/';
  var query = getQueryString(options);
  return baseURL + getHash(email) + '.' + format + query;
}
```
- example usage
```shell
...
'''javascript
var gravatar = require('gravatar');

gravatar.url(email);
gravatar.url(email, options);
gravatar.url(email, options, protocol);

gravatar.profile_url(email);
gravatar.profile_url(email, options);
gravatar.profile_url(email, options, protocol);
'''

## Where:
* 'email':
The gravatar email
...
```

#### <a name="apidoc.element.gravatar.url"></a>[function <span class="apidocSignatureSpan">gravatar.</span>url (email, options, protocol)](#apidoc.element.gravatar.url)
- description and source-code
```javascript
url = function (email, options, protocol) {
  var baseURL = "//www.gravatar.com/avatar/";
  if (options && options.protocol) protocol = proto(options);
  if(typeof protocol !== 'undefined') {
    baseURL = protocol ? "https://s.gravatar.com/avatar/" : 'http://www.gravatar.com/avatar/';
  }
  var query = getQueryString(options);
  return baseURL + getHash(email) + query;
}
```
- example usage
```shell
...

Usage
------

'''javascript
var gravatar = require('gravatar');

gravatar.url(email);
gravatar.url(email, options);
gravatar.url(email, options, protocol);

gravatar.profile_url(email);
gravatar.profile_url(email, options);
gravatar.profile_url(email, options, protocol);
'''
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
