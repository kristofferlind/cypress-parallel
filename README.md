[![npm version](https://badge.fury.io/js/cypress-parallel.svg)](https://badge.fury.io/js/cypress-parallel)

# cypress-parallel

Reduce up to 40% your Cypress suite execution time parallelizing the test run on the same machine.

| cypress | cypress-parallel |
:-------------------------:|:-------------------------:
| ![cy-serial-small](https://user-images.githubusercontent.com/38537547/114301114-92600a80-9ac3-11eb-9166-e95ae9cd5178.gif) | ![cy-parallel_small](https://user-images.githubusercontent.com/38537547/114301127-9db33600-9ac3-11eb-9bfc-c2096023bba7.gif) |


# Run your Cypress tests in parallel (locally)

## How it works

🔍 - Search for existing Cypress tests\
📄 - Read (if exists) a weight file\
⚖️ - Split spec files into different threads\
⚙️ - For each thread it runs the Cypress command you've passed as argument\
📈 - Wait for all threads to finish and collects the result in a single report

# How to use

## Install

```
npm i cypress-parallel
```

or

```
yarn add cypress-parallel
```

## Add a new script

In your `package.json` add a new script:

```typescript
"scripts" :{
  ...
  "cy:run": "cypress run", // It can be any cypress command with any argument
  "cy:parallel" : "cypress-parallel -s cy:run -t 2 -d <your-cypress-specs-folder> -a '\"<your-cypress-cmd-args>\"'"
  ...
}
```

### With Arguments

Sample:

```
-a '\"--config baseUrl=http://localhost:3000\"'
```

## Launch the new script

```
npm run cy:parallel
```

### Scripts options

| Option            | Alias | Description                        | Type   |
| ----------------- | ----- | ---------------------------------- | ------ |
| --help            |       | Show help                          |        |
| --version         |       | Show version number                |        |
| --script          | -s    | Your npm Cypress command           | string |
| --args            | -a    | Your npm Cypress command arguments | string |
| --threads         | -t    | Number of threads                  | number |
| --specsDir        | -d    | Cypress specs directory.           | string |
| --reporter        | -r    | Reporter to pass to Cypress.       | string |
| --reporterOptions | -o    | Reporter options                   | string |
| --bail            | -b    | Exit on first failing thread       | string |
| --verbose         | -v    | Some additional logging            | string |

# Contributors

Looking for contributors.

# License

MIT
