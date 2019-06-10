### 1. Executables
- index.js - main file for node launch
- savePrivateKey.js - file for private key saving (analogue of keystore)

### 2. Node launch
- **win**
- **mac**
- **from sources**

*Node launch for Linux:*
```
sudo apt update
sudo apt -y install npm
sudo npm i -g n
sudo n 10.15.2
git clone https://github.com/SilentNotaryEcosystem/Cil-core.git
cd Cil-core
git checkout tags/latest
npm i
```
- **docker**

### 3. Keys for node launch

By default, constants are set in the file prod.conf.js (for production network) и devel.conf.js (for development network). 

You can redefine them using keys:

|Key|Description|
|---|---|
|listenAddr|Defined address|
|port|Defined port|
|seedAddr|Seed address for node uploading|
|rpcUser|User name to call functions from node|
|rpcPass|Password to call functions from node|
|rpcPort|Port for call functions from node|
|rpcAddress|Address for call functions from node|
|genesisHash|Hash of genesis block for test enviroment settings|
|conciliumDefContract|Contract of genesis block for test enviroment settings|
|privateKey|File with private key for launch witness node|
|dbPath|Storage of database files directory|
|seed|Option: node will seed (will store and distribute peer adresses)|
|strictAddresses|Option: double IP-addreses connections will be closed|
|txIndex|Option: transaction index recieved by hash|
|watchAddress|Using for local wallets. Adds wallet addresses in node to track incoming and outgoing transactions to this address|
|reIndexWallet|Using for old wallets to receive all transactions from the database for the specified wallet address|
|walletSupport|Boolean defines does the node support wallets|
|listWallets|Service function using to show which addresses are added to the node|

### 4. Running a test network node
You must set the environment variable NODE_ENV to Devel.

Debug information output setting the variable DEBUG.

In components that support debugging at the beginning of the file there is a tag that is used for debug.

This is how the test network node is launched with debugging under linux.

```
NODE_ENV=Devel 
DEBUG=peer:*,node:* 
node index.js
```

### 5. Тестирование

* run tests ```npm test``` <br> 
if you want tonns of debug info
* run ```npm run-script testDebugNix``` for *nix
* run ```npm run-script testDebugWin``` for Windows
