# eth-gas-reporter

[![npm version](https://badge.fury.io/js/eth-gas-reporter.svg)](https://badge.fury.io/js/eth-gas-reporter)
[![Build Status](https://travis-ci.org/cgewecke/eth-gas-reporter.svg?branch=master)](https://travis-ci.org/cgewecke/eth-gas-reporter)

A mocha reporter for Truffle.

- Gas usage per unit test.
- Average gas usage per method.
- Contract deployment costs.
- Real currency costs.

![screen shot 2018-08-01 at 10 13 56 am](https://user-images.githubusercontent.com/7332026/43537357-f64f031e-9573-11e8-9348-315d9d4a8476.png)
![screen shot 2018-08-01 at 10 13 34 am](https://user-images.githubusercontent.com/7332026/43537353-f1889f70-9573-11e8-82c3-f93d3901db64.png)

### Install

```javascript
npm install --save-dev eth-gas-reporter
```

### Truffle config

```javascript
module.exports = {
  networks: {
    ...etc...
  },
  mocha: {
    reporter: 'eth-gas-reporter',
    reporterOptions : {
      currency: 'CHF',
      gasPrice: 21
    }
  }
};
```

### Options

| Option            | Type       | Default                              | Description                                                                                                                                                                               |
| ----------------- | ---------- | ------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| currency          | _String_   | 'EUR'                                | National currency to represent gas costs in. Exchange rates loaded at runtime from the `coinmarketcap` api. Available currency codes can be found [here](https://coinmarketcap.com/api/). |
| gasPrice          | _Number_   | (varies)                             | Denominated in `gwei`. Default is loaded at runtime from the `eth gas station` api                                                                                                        |
| outputFile        | _String_   | stdout                               | File path to write report output to                                                                                                                                                       |
| noColors          | _Boolean_  | false                                | Suppress report color. Useful if you are printing to file b/c terminal colorization corrupts the text.                                                                                    |
| onlyCalledMethods | _Boolean_  | true                                 | Omit methods that are never called from report.                                                                                                                                           |
| rst               | _Boolean_  | false                                | Output with a reStructured text code-block directive. Useful if you want to include report in RTD                                                                                         |
| rstTitle          | _String_   | ""                                   | Title for reStructured text header (See Travis for example output)                                                                                                                        |
| showTimeSpent     | _Boolean_  | false                                | Show the amount of time spent as well as the gas consumed                                                                                                                                 |
| excludeContracts  | _String[]_ | []                                   | Contract names to exclude from report. Ex: `['Migrations']`                                                                                                                               |
| src               | _String_   | "contracts"                          | Folder in root directory to begin search for `.sol` files. This can also be a path to a subfolder relative to the root, e.g. "planets/annares/contracts"                                  |
| url               | _String_   | value of `web3.currentProvider.host` | RPC client url (e.g. "http://localhost:8545") |
| proxyResolver | _Function_ | none | Custom method to resolve identity of methods managed by a proxy contract. |

### Examples

- [gnosis/gnosis-contracts](https://github.com/cgewecke/eth-gas-reporter/blob/master/docs/gnosis.md)
- [windingtree/LifToken](https://github.com/cgewecke/eth-gas-reporter/blob/master/docs/lifToken.md)

### Usage Notes

- Requires Node >= 8.
- Method calls that throw are filtered from the stats.
- Contracts that are only ever created by other contracts within Solidity are not shown in the deployments table.

### Contributions

Feel free to open PRs or issues. There is an integration test and one of the mock test cases is expected to fail. If you're adding an option, you can vaildate it in CI by adding it to the mock options config located [here](https://github.com/cgewecke/eth-gas-reporter/blob/master/mock/config-template.js#L13-L19).

### Credits

All the ideas in this utility have been borrowed from elsewhere. Many thanks to:

- [@maurelian](https://github.com/maurelian) - Mocha reporting gas instead of time is his idea.
- [@cag](https://github.com/cag) - The table borrows from / is based his gas statistics work for the Gnosis contracts.
- [Neufund](https://github.com/Neufund/ico-contracts) - Block limit size ratios for contract deployments and euro pricing are borrowed from their `ico-contracts` test suite.

### Contributors

- [@cgewecke](https://github.com/cgewecke)
- [@rmuslimov](https://github.com/rmuslimov)
- [@area](https://github.com/area)
- [@ldub](https://github.com/ldub)
- [@ben-kaufman](https://github.com/ben-kaufman)
- [@wighawag](https://github.com/wighawag)
- [@ItsNickBarry](https://github.com/ItsNickBarry)
