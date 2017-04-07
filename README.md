# api documentation for  [partialify (v3.1.6)](https://github.com/bclinkinbeard/partialify#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-partialify.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-partialify) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-partialify.svg)](https://travis-ci.org/npmdoc/node-npmdoc-partialify)
#### require()-able HTML, CSS, and (potentially) more

[![NPM](https://nodei.co/npm/partialify.png?downloads=true)](https://www.npmjs.com/package/partialify)

[![apidoc](https://npmdoc.github.io/node-npmdoc-partialify/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-partialify_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-partialify/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-partialify/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-partialify/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Ben Clinkinbeard"
    },
    "bugs": {
        "url": "https://github.com/bclinkinbeard/partialify/issues"
    },
    "dependencies": {
        "string-to-js": "0.0.1",
        "through": "^2.3.4"
    },
    "description": "require()-able HTML, CSS, and (potentially) more",
    "devDependencies": {
        "browserify": ">=3.24.1 <9.0.0",
        "tape": "^3.2.0"
    },
    "directories": {},
    "dist": {
        "shasum": "7f440f1dee92a85553f584e02bd9280570347d18",
        "tarball": "https://registry.npmjs.org/partialify/-/partialify-3.1.6.tgz"
    },
    "gitHead": "021eb7162433811a7d2d668ab2488fec1305cdd8",
    "homepage": "https://github.com/bclinkinbeard/partialify#readme",
    "keywords": [
        "browser",
        "browserify",
        "browserify-transform",
        "require",
        "static",
        "asset",
        "bundle",
        "partial"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "bclinkinbeard",
            "email": "ben.clinkinbeard@gmail.com"
        }
    ],
    "name": "partialify",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/bclinkinbeard/partialify.git"
    },
    "scripts": {
        "test": "tape test"
    },
    "version": "3.1.6"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module partialify](#apidoc.module.partialify)
1.  object <span class="apidocSignatureSpan">partialify.</span>custom

#### [module partialify.custom](#apidoc.module.partialify.custom)
1.  [function <span class="apidocSignatureSpan">partialify.custom.</span>alsoAllow (extensions)](#apidoc.element.partialify.custom.alsoAllow)
1.  [function <span class="apidocSignatureSpan">partialify.custom.</span>onlyAllow (extensions)](#apidoc.element.partialify.custom.onlyAllow)



# <a name="apidoc.module.partialify"></a>[module partialify](#apidoc.module.partialify)



# <a name="apidoc.module.partialify.custom"></a>[module partialify.custom](#apidoc.module.partialify.custom)

#### <a name="apidoc.element.partialify.custom.alsoAllow"></a>[function <span class="apidocSignatureSpan">partialify.custom.</span>alsoAllow (extensions)](#apidoc.element.partialify.custom.alsoAllow)
- description and source-code
```javascript
alsoAllow = function (extensions) {
  if (!Array.isArray(extensions)) extensions = Array.prototype.slice.call(arguments, 0);
  types = types.concat(extensions);
  return partialify;
}
```
- example usage
```shell
...
'''js
var b = require('browserify')(),
	fs = require('fs'),
	p = require('partialify/custom');

b.add('./entry.js');

b.transform(p.alsoAllow('xml'));
// or
b.transform(p.alsoAllow(['xml', 'csv']));
// or
b.transform(p.onlyAllow(['xml', 'csv']));

b.bundle().pipe(fs.createWriteStream('./bundle.js'));
'''
...
```

#### <a name="apidoc.element.partialify.custom.onlyAllow"></a>[function <span class="apidocSignatureSpan">partialify.custom.</span>onlyAllow (extensions)](#apidoc.element.partialify.custom.onlyAllow)
- description and source-code
```javascript
onlyAllow = function (extensions) {
  if (extensions) {
    if (!Array.isArray(extensions)) extensions = Array.prototype.slice.call(arguments, 0);

    types = extensions;
  }
  return partialify;
}
```
- example usage
```shell
...

b.add('./entry.js');

b.transform(p.alsoAllow('xml'));
// or
b.transform(p.alsoAllow(['xml', 'csv']));
// or
b.transform(p.onlyAllow(['xml', 'csv']));

b.bundle().pipe(fs.createWriteStream('./bundle.js'));
'''

### Customizing from the CLI

'browserify index.js -t [ partialify --alsoAllow svg --alsoAllow xml ] -o bundle.js'
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
