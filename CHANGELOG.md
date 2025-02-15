## Changelog: eth-gas-reporter

# 0.2.1 / 2019-06-19

- Upgrade mocha from 4.1.0 to 5.2.0
- Report solc version and settings info
- Add EtherRouter method resolver logic (as option and example)
- Add proxyResolver option & support discovery of delegated method calls identity
- Add draft of 0x artifact handler
- Add url option for non-truffle, non-buidler use
- Add buidler truffle-v5 plugin support (preface to gas-reporter plugin in next release)
- Completely reorganize and refactor

# 0.2.0 / 2019-05-07

- Add E2E tests in CI
- Restore logic that matches tx signatures to contracts as a fallback when it's impossible to
  be certain which contract was called (contribution @ItsNickBarry)
- Fix bug which crashed reporter when migrations linked un-deployed contracts

# 0.1.12 / 2018-09-14

- Allow contracts to share method signatures (contribution @wighawag)
- Collect gas data for Migrations deployments (contribution @wighawag)
- Add ability allow to specify a different src folder for contracts (contribution @wighawag)
- Handle in-memory provider error correctly / use spec reporter if sync calls impossible (contribution @wighawag)
- Default to only showing invoked methods in report

# 0.1.10 / 2018-07-18

- Update mocha from 3.5.3 to 4.10.0 (contribution ldub)
- Update truffle to truffle@next to fix mocha issues (contribution ldub)
- Modify binary checking to allow very long bytecodes / large contracts (contribution ben-kaufman)

# 0.1.9 / 2018-06-27

- Fix bug that caused test gas to include before hook gas consumption totals

# 0.1.8 / 2018-06-26

- Add showTimeSpent option to also show how long each test took (contribution @ldub)
- Update cli-table2 to cli-table3 (contribution @DanielRuf)

# 0.1.7 / 2018-05-27

- Support reStructured text code-block output

# 0.1.5 / 2018-05-15

- Support multi-contract files by parsing files w/ solidity-parser-antlr

# 0.1.4 / 2018-05-14

- Try to work around web3 websocket provider by attempting connection over http://.
  `requestSync` doesn't support this otherwise.
- Detect and identify binaries with library links, add to the deployments table
- Add scripts to run geth in CI (not enabled)

# 0.1.2 / 2018-04-20

- Make compatible with Web 1.0 by creating own sync RPC wrapper. (Contribution: @area)

# 0.1.1 / 2017-12-19

- Use mochas own reporter options instead of .ethgas (still supported)
- Add onlyCalledMethods option
- Add outputFile option
- Add noColors option

# 0.1.0 / 2017-12-10

- Require config gas price to be expressed in gwei (breaking change)
- Use eth gas station API for gas price (it's more accurate)
- Fix bug that caused table not to print if any test failed.

# 0.0.15 / 2017-12-09

- Fix ascii colorization bug that caused crashed during table generation. (Use colors/safe).

# 0.0.14 / 2017-11-30

- Fix bug that caused the error report at the end of test run not to be printed.

# 0.0.13 / 2017-11-15

- Filter throws by receipt.status if possible
- Use testrpc 6.0.2 in tests, add view and pure methods to tests.

# 0.0.12 / 2017-10-28

- Add config. Add gasPrice and currency code options
- Improve table clarity
- Derive block.gasLimit from rpc

# 0.0.11 / 2017-10-23

- Add Travis CI
- Fix bug that crashed reported when truffle could not find required file

# 0.0.10 / 2017-10-22

- Add examples

# 0.0.10 / 2017-10-22

- Filter deployment calls that throw from the stats

# 0.0.8 / 2017-10-22

- Filter method calls that throw from the stats
- Add deployment stats
- Add number of calls column

# 0.0.6 / 2017-10-14

- Stop showing zero gas usage in mocha output
- Show currency rates and gwei gas price rates in table header
  \* Alphabetize table
- Fix bug caused by unused methods reporting NaN
- Fix failure to round avg gas use in table
- Update dev deps to truffle4 beta

# 0.0.5 / 2017-10-12

- Thanks
- Update image
- Finish table formatting
- Add some variable gas consumption contracts
- Working table
- Get map to work in the runner
- Get gasStats file and percentage of limit working
- Test using npm install
- Add gasPrice data fetch, config logic
- More tests
- Abi encoding map.

# 0.0.4 / 2017-10-01

- Add visual inspection test
- Fix bug that counted gas consumed in the test hooks
