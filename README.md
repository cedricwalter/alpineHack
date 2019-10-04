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
apm install language-ethereum
apm install etheratom
```
Read more https://github.com/0mkara/etheratom

# Create your project
```
mkdir myprojectName
cd myprojectName
echo "# alpineHack smartcontract " >> README.md
truffle init
git init
git add .
git remote add origin https://github.com/AlpineHack/teamName.git
git push -u origin master
```

