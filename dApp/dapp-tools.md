

## Truffle suite/Embark/Remix/Zeppelin/EthPM




### 1.1. Truffle Suite

#### 1.1.1. ConsenSys

ConsenSys is a venture production studio that supports and grows a number of projects, platforms, and dapps building off the Ethereum blockchain (`ConsenSys`是一家企业生产工作室，支持并培育了许多依托于以太坊区块链的项目、平台以及去中心化应用).

ConsenSys's projects address every part of the Ethereum ecosystem, including (`ConsenSys`的项目涉及以太坊生态的每个部分，包括):

- crucial infrastructure projects(关键基础设施): Infura
- developer tools(开发者工具): Truffle
- core integration components(核心集成组件): MetaMask
- services(服务): Diligence
- B2C dapps: Grid+, Cellarius
- enterprise solutions(企业级解决方案): Kaleido

#### 1.2.2. Truffle

Just like we have frameworks for web application development such as Ruby on Rails, Python/Django etc, Truffle is the most popular frameworks used to develop dapps.

> https://github.com/trufflesuite/truffle

[Truffle 调研报告](https://github.com/wdx7266/learning-ethereum/blob/master/doc/Truffle/truffle_intro.md)
```shell
npm install -g truffle
```

Truffle是一个世界级的开发环境，测试框架，以太坊的资源管理通道，致力于让以太坊上的开发变得简单，Truffle有以下特点：
* 内置的智能合约编译，链接，部署和二进制文件的管理
* 快速开发下的自动合约测试
* 脚本化的，可扩展的部署与发布框架
* 部署到不同的公网或私网的网络环境管理功能
* 使用EthPM&NPM提供的包管理，使用ERC190标准
* 与合约直接通信的直接交互控制台（写完合约就可以命令行里验证了）
* 可配的构建流程，支持紧密集成

### 1.2. Embark

A framework for serverless Decentralized Applications using Ethereum, IPFS and other platforms. 

Embark 让开发者开发和部署以太坊dapp更容易，Embark当前集成了EVM区块链、去中心化存储IPFS、去中心化通信平台（Whisper和Orbit），支持swarm部署。

#### Embark框架特点
区块链（Ethereum）:

* 自动化的部署合约，方便js代码中调用。Embark可以自动监听合约的变化并重新部署变化后的合约。
* 合约可以通过js的promise调用
* 使用Javascript使用合约进行测试驱动开发。
* 追踪已经部署的合约，当合约更新的时候，会自动更新
* 管理不同链(testnet、private net,livenet)
* 轻松管理相互依赖合同的复杂系统

去中心化存储（IPFS）:
* 通过EmbarkJS轻松存储和检索DApp上的数据。 包括上传和检索文件。
* 将完整的应用程序部署到IPFS或Swarm。 去中心化通信（Whisper, Orbit）:
* 通过Whisper或Orbit轻松通过P2P渠道发送/接收消息。

web 技术:

* 与任何网络技术集成，包括React，Foundation等。
* 使用您想要的任何构建管道或工具，包括grunt，gulp和webpack。

> https://embark.status.im/

```shell
npm install -g embark
```

### 1.3. Metamask

It is unrealistic for everyone in the world to run a node to interact with the blockchain. So, the folks at Metamask host a number of nodes so you don’t have to. All you have to do is install Metamask and it automatically connects to their nodes.

> https://metamask.io/

[MetaMask调研报告](https://github.com/wdx7266/learning-ethereum/tree/master/doc/MetaMask)

![ethereumMetamaskChrome](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/ethereumMetamaskChrome.png)

> Github: https://github.com/MetaMask

[MetaMask](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/metamask.png)

![metaMaskPhishing](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/metaMaskPhishing.png)

### 1.4. Remix

Remix is a browser-based compiler and IDE that enables users to build Ethereum contracts with Solidity language and to debug transactions.

![Remix](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/Remix.png)

> https://github.com/ethereum/remix-ide

[Remix调研报告](https://github.com/wdx7266/learning-ethereum/tree/master/doc/IDE)


### 1.5. Populs

Development framework for Ethereum smart contracts.

> https://github.com/ethereum/populus

```shell
pip install populus
```

### 1.6. Zeppelin

> https://zeppelin.solutions/

![zeppelin](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/zeppelin.png)

#### 1.6.1. OpenZeppelin

A framework of modular, reusable, secure smart contracts for the Ethereum network, written in Solidity.

#### 1.6.2. ZeppelinOS

A distributed platform of tools and services to develop and manage smart contract applications securely.

### 1.7. Oyente

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





