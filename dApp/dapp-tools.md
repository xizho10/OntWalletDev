

## Truffle suite/Embark/Remix/Zeppelin/EthPM


### 1.4. Embark

A framework for serverless Decentralized Applications using Ethereum, IPFS and other platforms. 

> https://embark.status.im/

```shell
npm install -g embark
```

### 1.5. Truffle Suite

#### 1.5.1. ConsenSys

ConsenSys is a venture production studio that supports and grows a number of projects, platforms, and dapps building off the Ethereum blockchain (`ConsenSys`是一家企业生产工作室，支持并培育了许多依托于以太坊区块链的项目、平台以及去中心化应用).

ConsenSys's projects address every part of the Ethereum ecosystem, including (`ConsenSys`的项目涉及以太坊生态的每个部分，包括):

- crucial infrastructure projects(关键基础设施): Infura
- developer tools(开发者工具): Truffle
- core integration components(核心集成组件): MetaMask
- services(服务): Diligence
- B2C dapps: Grid+, Cellarius
- enterprise solutions(企业级解决方案): Kaleido

#### 1.5.2. Truffle

Just like we have frameworks for web application development such as Ruby on Rails, Python/Django etc, Truffle is the most popular frameworks used to develop dapps.

> https://github.com/trufflesuite/truffle

```shell
npm install -g truffle
```



### 1.6. Metamask

It is unrealistic for everyone in the world to run a node to interact with the blockchain. So, the folks at Metamask host a number of nodes so you don’t have to. All you have to do is install Metamask and it automatically connects to their nodes.

> https://metamask.io/

![ethereumMetamaskChrome](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/ethereumMetamaskChrome.png)

> Github: https://github.com/MetaMask

![MetaMask](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/metamask.png)

![metaMaskPhishing](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/metaMaskPhishing.png)

## 2. Remix

Remix is a browser-based compiler and IDE that enables users to build Ethereum contracts with Solidity language and to debug transactions.

![Remix](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/Remix.png)

> https://github.com/ethereum/remix-ide




## 3. Populs

Development framework for Ethereum smart contracts.

> https://github.com/ethereum/populus

```shell
pip install populus
```

## 4. Zeppelin

> https://zeppelin.solutions/

![zeppelin](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/zeppelin.png)

### 4.1. OpenZeppelin

A framework of modular, reusable, secure smart contracts for the Ethereum network, written in Solidity.

### 4.2. ZeppelinOS

A distributed platform of tools and services to develop and manage smart contract applications securely.

## 5. Oyente

An Analysis Tool for Smart Contracts based on Python.

> Github: https://github.com/melonproject/oyente

> Official Website: https://oyente.melonport.com/





## 6. EthPM

> https://www.ethpm.com/

A package manager for Ethereum.

- Get started with Truffle:

```shell
npm install truffle
truffle install owned
```

- Get started with Populus:

```shell
pip install populus
populus package install owned
```

***
Install a package from the Ethereum Package Registry.

```shell
truffle install [package_name]<@version>
```

Parameters:

- `package_name`: Name of the package as listed in the Ethereum Package Registry.

Optional parameters:

- `<@version>`: When specified, will install a specific version of the package, otherwise will install the latest version.

```shell
C:\Truffle> truffle install bytes
C:\Truffle\installed_contracts> tree /F
C:.
└─bytes
    │  ethpm.json
    │  lock.json
    │  lock.uri
    │
    └─contracts
            AssertBytes.sol
            BytesLib.sol
            Migrations.sol
```

```json
// ethpm.json

{
  "authors": [
    "Gonçalo Sá <goncalo.sa@consensys.net>"
  ],
  "license": "MIT",
  "description": "Solidity bytes tightly packed arrays utility library.",
  "keywords": [
    "bytes",
    "utils",
    "solidity",
    "library"
  ],
  "links": {},
  "sources": [
    "./contracts/AssertBytes.sol",
    "./contracts/BytesLib.sol",
    "./contracts/Migrations.sol"
  ],
  "dependencies": {},
  "manifest_version": 1,
  "package_name": "bytes",
  "version": "0.0.5"
}
```

```json
// lock.json

{
    "lockfile_version":"1",
    "package_name":"bytes",
    "meta":{
        "authors":[
            "Gonçalo Sá <goncalo.sa@consensys.net>"
        ],
        "license":"MIT",
        "description":"Solidity bytes tightly packed arrays utility library.",
        "keywords":[
            "bytes",
            "utils",
            "solidity",
            "library"
        ],
        "links":{

        }
    },
    "version":"0.0.5",
    "contract_types":{
        "undefined":{
            "abi":[
                {
                    "constant":false,
                    "inputs":[
                        {
                            "name":"new_address",
                            "type":"address"
                        }
                    ],
                    "name":"upgrade",
                    "outputs":[

                    ],
                    "payable":false,
                    "stateMutability":"nonpayable",
                    "type":"function"
                },
                {
                    "constant":true,
                    "inputs":[

                    ],
                    "name":"last_completed_migration",
                    "outputs":[
                        {
                            "name":"",
                            "type":"uint256"
                        }
                    ],
                    "payable":false,
                    "stateMutability":"view",
                    "type":"function"
                },
                {
                    "constant":true,
                    "inputs":[

                    ],
                    "name":"owner",
                    "outputs":[
                        {
                            "name":"",
                            "type":"address"
                        }
                    ],
                    "payable":false,
                    "stateMutability":"view",
                    "type":"function"
                },
                {
                    "constant":false,
                    "inputs":[
                        {
                            "name":"completed",
                            "type":"uint256"
                        }
                    ],
                    "name":"setCompleted",
                    "outputs":[

                    ],
                    "payable":false,
                    "stateMutability":"nonpayable",
                    "type":"function"
                },
                {
                    "inputs":[

                    ],
                    "payable":false,
                    "stateMutability":"nonpayable",
                    "type":"constructor"
                }
            ]
        }
    },
    "deployments":{

    },
    "sources":{
        "./contracts/AssertBytes.sol":"ipfs://QmeCL2h74Y54vDG86FhYKJRAKgiym1oip5jnY6kCAfMYUd",
        "./contracts/BytesLib.sol":"ipfs://QmSVkF45NQJEETdbX1zmp5EXFmzCURLW9Bcqr7wnV5bC2p",
        "./contracts/Migrations.sol":"ipfs://QmZ72TqAAmZA1fBze7HBpRP6XspG7g62JzTbAb1pAX8AVs"
    },
    "build_dependencies":{

    }
}
```

***

![EthPM](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/EthPM.png)

- [`Py-EthPM`](https://github.com/ethpm/py-ethpm): A Python implementation of the [Ethereum Package Manager Specification](https://github.com/ethpm/ethpm-spec).

```shell
pip install ethpm
```

- [`ethpm.js`](https://github.com/ethpm/py-ethpm): Work in progress library for interacting with EthPM packages in Javascript and TypeScript.

> https://github.com/ethpm/ethpm.js

- [`ethpm-go`](https://github.com/ethpm/ethpm-go): A go package which provides an EthPM v2 package manifest reader and writer.



### 7.4. Aleth

The collection of C++ libraries and tools for Ethereum, formerly known as cpp-ethereum project. This includes the full Ethereum client aleth.

> Github: https://github.com/ethereum/aleth

> Docs: http://www.ethdocs.org/en/latest/ethereum-clients/cpp-ethereum/





