# Commitlint issue reproduction

## Steps

- Clone repo
- Make change
- try commit
```
git commit -am "some changes"
```
- error
```
TypeError [ERR_INVALID_ARG_TYPE]: The "path" argument must be of type string. Received undefined
    at new NodeError (node:internal/errors:372:5)
    at validateString (node:internal/validators:120:11)
    at Object.join (node:path:1172:7)
    at getLernaVersion (/Users/gvdp/code/oss/lerna-commitlint/node_modules/@commitlint/config-lerna-scopes/index.js:57:22)
    at /Users/gvdp/code/oss/lerna-commitlint/node_modules/@commitlint/config-lerna-scopes/index.js:33:25
    at async execute (/Users/gvdp/code/oss/lerna-commitlint/node_modules/@commitlint/execute-rule/src/index.ts:20:16)
    at async Promise.all (index 0)
    at async load (/Users/gvdp/code/oss/lerna-commitlint/node_modules/@commitlint/load/src/load.ts:78:3)
    at async main (/Users/gvdp/code/oss/lerna-commitlint/node_modules/@commitlint/cli/src/cli.ts:214:17) {
  code: 'ERR_INVALID_ARG_TYPE'
}
husky - commit-msg hook exited with code 1 (error)
```

seems related to https://github.com/sindresorhus/resolve-pkg/issues/9 ?
