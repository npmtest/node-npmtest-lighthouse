# npmtest-lighthouse

#### basic test coverage for  [lighthouse (v1.6.3)](https://github.com/GoogleChrome/lighthouse#readme)  [![npm package](https://img.shields.io/npm/v/npmtest-lighthouse.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-lighthouse) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-lighthouse.svg)](https://travis-ci.org/npmtest/node-npmtest-lighthouse)

#### Lighthouse

[![NPM](https://nodei.co/npm/lighthouse.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/lighthouse)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-lighthouse/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-lighthouse/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-lighthouse/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-lighthouse/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-lighthouse/build/test-report.html)|
| build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-lighthouse/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-lighthouse/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-lighthouse/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-lighthouse/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-lighthouse/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-lighthouse/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-lighthouse/build/test-report.html](https://npmtest.github.io/node-npmtest-lighthouse/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-lighthouse/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-lighthouse/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-lighthouse/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-lighthouse/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-lighthouse/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-lighthouse/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-lighthouse/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-lighthouse/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "lighthouse",
    "version": "1.6.3",
    "description": "Lighthouse",
    "main": "./lighthouse-core/index.js",
    "bin": {
        "lighthouse": "./lighthouse-cli/index.js",
        "chrome-debug": "./lighthouse-cli/manual-chrome-launcher.js"
    },
    "engines": {
        "node": ">=6"
    },
    "scripts": {
        "install-all": "npm run install-cli && npm run install-extension && npm run install-viewer",
        "install-cli": "cd ./lighthouse-cli && npm install",
        "install-extension": "cd ./lighthouse-extension && npm install",
        "install-viewer": "cd ./lighthouse-viewer && npm install",
        "build-all": "npm run build-cli && npm run build-extension && npm run build-viewer",
        "build-cli": "cd ./lighthouse-cli && npm run build",
        "build-extension": "cd ./lighthouse-extension && npm run build",
        "build-viewer": "cd ./lighthouse-viewer && npm run build",
        "lint": "[ \"$CI\" = true ] && eslint --quiet -f codeframe . || eslint .",
        "smoke": "bash lighthouse-cli/test/smokehouse/offline-local/run-tests.sh && bash lighthouse-cli/test/smokehouse/dobetterweb/run-tests.sh && bash lighthouse-cli/test/smokehouse/byte-efficiency/run-tests.sh",
        "coverage": "node $(npm bin)/istanbul cover -x \"**/third_party/**\" _mocha -- $(find */test -name '*-test.js') --timeout 10000 --reporter progress",
        "coveralls": "npm run coverage && cat ./coverage/lcov.info | coveralls",
        "start": "node ./lighthouse-cli/index.js",
        "test": "npm run lint --silent && npm run unit",
        "core-unit": "bash lighthouse-core/scripts/run-mocha.sh --core",
        "cli-unit": "bash lighthouse-core/scripts/run-mocha.sh --cli",
        "viewer-unit": "bash lighthouse-core/scripts/run-mocha.sh --viewer",
        "unit": "bash lighthouse-core/scripts/run-mocha.sh --default",
        "closure": "cd lighthouse-core && node closure/closure-type-checking.js",
        "watch": "bash lighthouse-core/scripts/run-mocha.sh --watch",
        "chrome": "node ./lighthouse-cli/manual-chrome-launcher.js",
        "fast": "npm run start -- --disable-device-emulation --disable-cpu-throttling --disable-network-throttling",
        "smokehouse": "node lighthouse-cli/test/smokehouse/smokehouse.js",
        "deploy-viewer": "cd lighthouse-viewer && gulp deploy"
    },
    "devDependencies": {
        "@types/node": "^6.0.45",
        "babel-core": "^6.16.0",
        "babel-plugin-transform-es2015-destructuring": "^6.9.0",
        "coveralls": "^2.11.9",
        "eslint": "^3.12.0",
        "eslint-config-google": "^0.7.1",
        "google-closure-compiler": "^20161201.0.0",
        "gulp": "^3.9.1",
        "gulp-replace": "^0.5.4",
        "gulp-util": "^3.0.7",
        "istanbul": "^0.4.3",
        "jsdom": "^9.0.0",
        "mocha": "^3.2.0",
        "walk": "^2.3.9",
        "zone.js": "^0.7.3"
    },
    "dependencies": {
        "axe-core": "2.1.7",
        "chrome-devtools-frontend": "1.0.422034",
        "debug": "2.2.0",
        "devtools-timeline-model": "1.1.6",
        "gl-matrix": "2.3.2",
        "handlebars": "4.0.5",
        "json-stringify-safe": "5.0.1",
        "marked": "0.3.6",
        "metaviewport-parser": "0.0.1",
        "mkdirp": "0.5.1",
        "opn": "4.0.2",
        "rimraf": "2.2.8",
        "semver": "5.3.0",
        "speedline": "1.0.3",
        "whatwg-url": "4.0.0",
        "ws": "1.1.1",
        "yargs": "3.32.0"
    },
    "repository": "GoogleChrome/lighthouse",
    "keywords": [
        "google",
        "chrome",
        "devtools"
    ],
    "author": "The Chromium Authors",
    "license": "Apache-2.0",
    "bugs": {
        "url": "https://github.com/GoogleChrome/lighthouse/issues"
    },
    "homepage": "https://github.com/GoogleChrome/lighthouse#readme"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
