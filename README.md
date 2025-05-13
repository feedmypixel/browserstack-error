# Browserstack error

Minimal repo example. When trying to set up `browserstack-node-sdk` and running through the following steps to reproduce. I get the error
```javascript
error: TypeError: Cannot read properties of null (reading 'split')
```

## Setup
- `Node v22.13.1`
- `npm v11.3.0`
- `MacOS Sonoma 14.7.2`

## Steps to reproduce
- Using [Integrate Percy with Selenium and JestJS](https://www.browserstack.com/docs/percy/integrate-bstack-sdk/jest) as a reference
- `npm i`
- `npm run test:browserstack`
- Observe the following error:
```javascript
$ npm run test:browserstack

> percy-try@0.1.0 test:browserstack
> browserstack-node-sdk jest

2025-05-13 10:22:13 - info: Reading configs from /Users/**/**/percy-try/browserstack.yml
2025-05-13 10:22:13 - info: Log Directory has been set to /Users/**/**/percy-try/log
2025-05-13 10:22:13 - info: Running SDK with args /Users/**/.nvm/versions/node/v22.13.1/bin/node /Users/**/**/percy-try/node_modules/.bin/browserstack-node-sdk jest
2025-05-13 10:22:13 - info: SDK run started with id: bfafa68c-89a2-4841-bc76-3368d23955ff
2025-05-13 10:22:13 - error: TypeError: Cannot read properties of null (reading 'split')
at exports.<computed> [as compareVersions] (/Users/**/**/percy-try/node_modules/browserstack-node-sdk/src/helpers/helper.js:1:155470)
  at BrowserStackSetup.preInitialize (/Users/**/**/percy-try/node_modules/browserstack-node-sdk/src/helpers/BrowserStackSetup.js:1:11335)
  at BrowserStackSetup.initialize (/Users/**/**/percy-try/node_modules/browserstack-node-sdk/src/helpers/BrowserStackSetup.js:1:13228)
  at run (/Users/**/**/percy-try/node_modules/browserstack-node-sdk/src/bin/jest/command.js:2:5755)
  at Object.ZSLCZ (/Users/**/**/percy-try/node_modules/browserstack-node-sdk/src/bin/runner.js:2:1430)
  at captureError (/Users/**/**/percy-try/node_modules/browserstack-node-sdk/src/bin/runner.js:2:1592)
  at Object.lywtu (/Users/**/**/percy-try/node_modules/browserstack-node-sdk/src/bin/runner.js:2:5951)
  at /Users/**/**/percy-try/node_modules/browserstack-node-sdk/src/bin/runner.js:2:6353
  at _.applyBuilderUpdateUsageAndParse (/Users/**/**/percy-try/node_modules/yargs/build/index.cjs:1:7435)
  at _.runCommand (/Users/**/**/percy-try/node_modules/yargs/build/index.cjs:1:7078)
```

### Tried

- I dropped to `Node v20`
- I tried [1.35.4](https://www.npmjs.com/package/browserstack-node-sdk/v/1.35.4)

Both resulted in the same error
