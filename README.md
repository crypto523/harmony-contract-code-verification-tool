# Harmony-One Contract Verification Tool

A verification contract tool which compares byte code written on an address with byte code compiled by the tool from source code provided as a Github link to a .sol file

## Dependencies

Install the (global) dependencies
```
yarn
npm
truffle
```
For Debian-based systems:
```bash
sudo apt install npm
sudo npm install --global npm yarn truffle
```

## Installation

Once the dependencies are installed, clone the repository and do a ``yarn build``
```bash
git clone https://github.com/MaxMustermann2/harmony-contract-code-verification-tool.git
cd harmony-contract-code-verification-tool/
yarn
yarn build
```

## Usage
Run ```yarn start --help``` to see the help options
```
Usage:  verify|v command <options>

(default) Verifies if the given contract address byte code matches that generated by the tool

Options:
  -ca, --contractAddress <contractAddress>  The address of the contract
  -sv, --solidityVersion <solidityVersion>  The version of the Solidity compiler which was used to compile the contract (at deployment)
  -gu, --githubURL <githubURL>              Github Repository URL, up to and including the *.sol file
  -ch, --commitHash <commitHash>            (optional) Hash of the commit to check out
  -k, --keep                                (optional,default=false) Keep the Github repository after the process
  -c, --chainType <chainType>               Chain type, for example, testnet or mainnet
  -h, --help                                display help for command
```

Run the below to verify a contract:
```bash
yarn start verify --contractAddress one1rcs4yy4kln53ux60qdeuhhvpygn2sutn500dhw --githubURL https://github.com/rachit2501/Lottery-System/blob/master/contracts/Lottery.sol --chainType testnet --solidityVersion 0.4.17
```

## Tests
Simply run ```yarn test test/test.js --collectCoverage``` to view test coverage and results
