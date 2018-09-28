# DApp调研

[dApp定鑫调研分享](https://github.com/wdx7266/learning-ethereum/blob/master/doc/DApp/dappInEthereumEcosystem.md),[dApp帅帅调研分享](https://github.com/lucas7788/workingdata/tree/master/blockchaingames/ethereum)

dApp调研任务：

* [SC Tools](dapp-tools.md): Truffle suite/Embark/Remix/Zeppelin/EthPM   ——**周喜**、**帅帅**、**定鑫**。帅帅调研跨链
* [Boilerplates](dapp-boilerplates.md) : Drizzle                     ——**大双**、**沈寅**
* [Dapps web](dapp-web.md): etherscan/parity/MIST/State of Dapps                ——**苏凌霄**、**李颖轩**
* [Blockchain ui and IPFS](dapp-blockchain.md): Geth/Ganache/IPFS   ——**底层**
* Dapps                                                                  ——**周强**提供后台服务。


##  以太坊开发工具集

* Mist Mist的功能包括保存以太币、发送交易、部署合约等。你可以用它实现与区块链平台或测试网络
的交互。当你需要进行快速交易时超级有用
* Geth Geth除了实现Mist的全部功能，还包含一些额外的重要特性，例如提供RPC API接口给应用程序以便你的应用可以通过它连接如以太坊网络。
* Parity Parity是一个用Rust开发的以太坊节点软件，开发者是前以太坊CTO：Gavin Wood博士。Parity 的特点就是速度块、轻量化。Parity 还在本机的8080 端口提供了一个Web界面供你访问。
parity特点:
  1. parity 使用Rust开发，异步调用效率较高
  2. parity对以太坊历史数据做了优化，同步历史数据更快
  3. parity内置POA、tendermint等共识引擎，可以搭建自己的链
  4. parity提供图形化的客户端进行合约开发、调试和调用
  5. parity加入了一些黑科技，比如定时发送交易，快速切换测试网络
* MetaMask Chrome浏览器插件
* Web3.js  Web3.js是web应用和区块链交互的桥梁
* Truffle 提供了快速创建、编译、部署和测试区块链应用的构建模块
* Solc 是以太坊智能合约编译器，可以把合约代码编译成以太坊字节码
* Solium solidity代码静态分析器，可以帮助开发者规范代码并发现安全隐患
* ether.camp 微软提供的在线全功能solidity集成开发环境
* BlockApps BlockApps提供了一些简洁的API来帮助你查看钱包余额、编写交易、读取合约状态等
* Embark Embark是另一个流行的开发框架，帮你轻松地构建、测试和部署DApp
* Zeppelin Zeppelin库用来编写安全的合约(类似于Java中的jar包，在合约中可以引入智能合约语言开发的工具库)

## Dapps:


[CryptoKitties](https://github.com/wdx7266/learning-ethereum/blob/master/doc/DApp/cryptoKitties.md)
[Bancor协议Token]()
[Fomo3D]()
