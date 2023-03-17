## Learning to run tap in TypeScript

this is a simple project in order to learn how to use [`tap`](https://node-tap.org/docs/tap-files/) with Typescript

## Solution

a quick solution was presented https://github.com/tapjs/node-tap/issues/679#issuecomment-1472442741

that made things working correctly with a bit tweaking that can be seen on https://github.com/balexandre/testing-tap/pull/1

## Error (original error for history)

if one runs `npm i` and then `npm test` this is the error that the test throws

```bash
./test/ping.spec.ts 2> TypeError [ERR_UNKNOWN_FILE_EXTENSION]: Unknown file extension ".ts" for /home/balexandre/Repositories/tap/test/ping.spec.ts
./test/ping.spec.ts 2>     at new NodeError (node:internal/errors:399:5)
./test/ping.spec.ts 2>     at Object.getFileProtocolModuleFormat [as file:] (node:internal/modules/esm/get_format:79:11)
./test/ping.spec.ts 2>     at defaultGetFormat (node:internal/modules/esm/get_format:121:38)
./test/ping.spec.ts 2>     at defaultLoad (node:internal/modules/esm/load:81:20)
./test/ping.spec.ts 2>     at nextLoad (node:internal/modules/esm/loader:163:28)
./test/ping.spec.ts 2>     at ESMLoader.load (node:internal/modules/esm/loader:605:26)
./test/ping.spec.ts 2>     at ESMLoader.moduleProvider (node:internal/modules/esm/loader:457:22)
./test/ping.spec.ts 2>     at new ModuleJob (node:internal/modules/esm/module_job:64:26)
./test/ping.spec.ts 2>     at ESMLoader.#createModuleJob (node:internal/modules/esm/loader:480:17)
./test/ping.spec.ts 2>     at ESMLoader.getModuleJob (node:internal/modules/esm/loader:434:34) {
./test/ping.spec.ts 2>   code: 'ERR_UNKNOWN_FILE_EXTENSION'
./test/ping.spec.ts 2> }
​ FAIL ​ ./test/ping.spec.ts 255.894ms
  command: /home/balexandre/.nvm/versions/node/v18.14.0/bin/node
  args:
    - -r
    - /home/balexandre/Repositories/tap/node_modules/ts-node/register/index.js
    - ./test/ping.spec.ts
  exitCode: 1
  signal: null

​ FAIL ​ TAP
 ✖ ./test/ping.spec.ts

  test: TAP
  env:
    TS_NODE_COMPILER_OPTIONS: "{}"
  file: ./test/ping.spec.ts
  timeout: 30000
  command: /home/balexandre/.nvm/versions/node/v18.14.0/bin/node
  args:
    - -r
    - /home/balexandre/Repositories/tap/node_modules/ts-node/register/index.js
    - ./test/ping.spec.ts
  stdio:
    - 0
    - pipe
    - 2
  cwd: /home/balexandre/Repositories/tap
  exitCode: 1



                         
  🌈 SUMMARY RESULTS 🌈  
                         
​ FAIL ​ ./test/ping.spec.ts 255.894ms
  command: /home/balexandre/.nvm/versions/node/v18.14.0/bin/node
  args:
    - -r
    - /home/balexandre/Repositories/tap/node_modules/ts-node/register/index.js
    - ./test/ping.spec.ts
  exitCode: 1
  signal: null


Suites:   ​1 failed​, ​1 of 1 completed​
Asserts:  ​​​1 failed​, ​of 1​
​Time:​   ​393.891ms​----------|---------|----------|---------|---------|-------------------
File      | % Stmts | % Branch | % Funcs | % Lines | Uncovered Line #s 
----------|---------|----------|---------|---------|-------------------
All files |       0 |        0 |       0 |       0 |                   
----------|---------|----------|---------|---------|-------------------
```