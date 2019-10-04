# alpineHack

we will install
* NodeJS and NPM: NodeJS is a server-side JavaScript platform to create apps that will help to communicate with your ethereum node.
* Truffle: Truffle is build framework used to compile, test and deploy your smart contract. It helps for faster development life cycle
* Atom: To write your smart contracts install Atom (but you can use your favorite text editor)

# Install NodeJS & NPM
If you already have the latest versions installed then skip this step or if you have an older version then plan to update it to the latest version.
To install NodeJS use below command,
## MacOs
```
brew install node
```
## Download Linux/Windows
https://nodejs.org/en/download/
## check proper installation, run in terminal
```
node -v
npm -v
```
# Install truffle
https://www.trufflesuite.com/truffle

# Install Atom
https://github.com/atom/atom

## Now open the terminal and type below command to install the extension in Atom for solidity support
```
apm install language-solidity
apm install etheratom
```
Read more https://github.com/0mkara/etheratom  NOTE: we wont use etheratom to deploy but truffle

# Create your project
this initialize truffle and make the folder a git repository
```
mkdir myProjectName
cd myProjectName
echo "# alpineHack smartcontract " >> README.md
truffle init
git init
git add .
git remote add origin https://github.com/AlpineHack/teamName.git
git push -u origin master
```
# Use Atom to open your project
File - Open - Select Folder /myProjectName

add a new file package.json
```
{
  "name": "myProjectName",
  "version": "1.0.0",
  "description": "myProjectName",
  "private": true,
  "license": "UNLICENSED",
  "engines": {
    "node": "^10.0.x"
  },
  "scripts": {
    "compile": "truffle compile",
  },
  "dependencies": {
    "openzeppelin-solidity": "2.3.0"
  },
  "devDependencies": {
    "bignumber.js": "^8.1.1",
    "bn-chai": "^1.0.1",
    "chai": "^4.2.0",
    "chai-as-promised": "^7.1.1",
    "chai-string": "^1.5.0",
    "dirty-chai": "^2.0.1",
    "coveralls": "^3.0.1",
    "eslint": "^4.19.1",
    "eslint-config-standard": "^10.2.1",
    "eslint-plugin-import": "^2.13.0",
    "eslint-plugin-mocha-no-only": "^1.1.0",
    "eslint-plugin-node": "^5.2.1",
    "eslint-plugin-promise": "^3.8.0",
    "eslint-plugin-standard": "^3.1.0",
    "eth-gas-reporter": "^0.1.12",
    "ganache-core": "^2.5.3",
    "truffle": "^5.0.8",
    "truffle-flattener": "^1.3.0",
    "truffle-hdwallet-provider": "^1.0.5",
    "web3-utils": "^1.0.0-beta.50",
    "pre-commit": "^1.2.2",
    "ganache-cli": "6.1.8",
    "ethereumjs-util": "^6.0.0",
    "solidity-coverage": "^0.5.11"
  },
  "optionalDevDependencies": {
    "fsevents": "*"
  }
}
```

Edit file truffle-config.js

```
/**
 * Truffle configuration
 *
 * @see https://github.com/trufflesuite/truffle-config/blob/master/index.js
 * @see https://github.com/trufflesuite/truffle/releases
 */
const HDWalletProvider = require('truffle-hdwallet-provider');

module.exports = {

    solc: {
        optimizer: {
            enabled: true,
            runs: 200
        }
    },
    networks: {
        _development: {
            host: 'localhost',
            port: 9545,
            network_id: 4447,
            gasPrice: 1,
            gas: 4700000
        },
        local: {
            host: 'localhost',
            port: 8547,
            network_id: '*',
            gasPrice: 1,
            gas: 6712390
        },
        ropsten: {
            provider: new HDWalletProvider("PrivateKeyAskMe", "https://ropsten.infura.io/"),
            network_id: 3,
            gasPrice: 10000000000,
            gas: 4712394
        }
    },
    compilers: {
        solc: {
            version: '0.5.12',
            docker: false,
            optimizer: {
                enabled: true,
                runs: 400
            }
        }
    }
};
```
