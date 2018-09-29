## Drizzle


#### 1.5.4. Drizzle

A collection of front-end libraries that make writing dapp front-ends easier and more predictable. The core of Drizzle is based on a Redux store, so you have access to the spectacular development tools around Redux. We take care of synchronizing your contract data, transaction data and more.

> Redux是一个用于应用程序状态管理的开源JavaScript库。

> Redux经常与React搭配运用，但其也可以独立使用。

> English Document: https://redux.js.org/

> 中文文档：http://www.redux.org.cn/




## API

### 1. Web3.js

Web3.js is an Ethereum JavaScript API.

Just like we have geth, mist browser and so on to communicate with the ethereum node, there is also a javascript library called Web3.js which can be used to interact with a node. Since it is a javascript library, we can use it to build web based dapps.

### 2. Web3.py

A python interface for interacting with the Ethereum blockchain and ecosystem. 

https://github.com/ethereum/web3.py

```python
import json
import web3

from web3 import Web3, HTTPProvider, TestRPCProvider
from solc import compile_source
from web3.contract import ConciseContract

# Solidity source code
contract_source_code = '''
pragma solidity ^0.4.0;

contract Greeter {
    string public greeting;

    function Greeter() {
        greeting = 'Hello';
    }

    function setGreeting(string _greeting) public {
        greeting = _greeting;
    }

    function greet() constant returns (string) {
        return greeting;
    }
}
'''

compiled_sol = compile_source(contract_source_code) # Compiled source code
contract_interface = compiled_sol['<stdin>:Greeter']

# web3.py instance
w3 = Web3(TestRPCProvider())

# Instantiate and deploy contract
contract = w3.eth.contract(abi=contract_interface['abi'], bytecode=contract_interface['bin'])

# Get transaction hash from deployed contract
tx_hash = contract.deploy(transaction={'from': w3.eth.accounts[0], 'gas': 410000})

# Get tx receipt to get contract address
tx_receipt = w3.eth.getTransactionReceipt(tx_hash)
contract_address = tx_receipt['contractAddress']

# Contract instance in concise mode
abi = contract_interface['abi']
contract_instance = w3.eth.contract(address=contract_address, abi=abi,ContractFactoryClass=ConciseContract)

# Getters + Setters for web3.eth.contract object
print('Contract value: {}'.format(contract_instance.greet()))
contract_instance.setGreeting('Nihao', transact={'from': w3.eth.accounts[0]})
print('Setting value to: Nihao')
print('Contract value: {}'.format(contract_instance.greet()))
```

![web3Py](https://raw.githubusercontent.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/web3Py.png)

### 3. web3j

web3j is a lightweight, highly modular, reactive, type safe Java and Android library for working with Smart Contracts and integrating with clients (nodes) on the Ethereum network:

![Alt text](https://raw.githubusercontent.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/web3jNetwork.png)

> https://web3j.io/

> https://github.com/web3j/web3j



## dapp开发框架初步设计


dapp开发主要分为智能合约开发和UI开发。（这里UI开发指完整的web项目，可能包括后台部分）

### 智能合约开发

#### 1.合约编辑器

Smartx 集合了合约编辑，部署，调用，调试（开发中，即将上线），支持主网，测试网，和本地网络多种环境。

仍然欠缺的是：合约完整测试工具，如根据配置文件，填充好参数，调整方法调用顺序，即可一次性测试合约所有方法。如果smartx上不能很好集成这个功能，可以在其他工具中提供。

#### 2.合约安全保障

相关工作进行中

### UI开发

dapp开发最常见最快速的是web开发。现在有很多流行的UI框架和工具，极大便利了开发者开发各种web应用。

以react和vue为代表的，都是数据驱动页面显示更新的框架。在状态数据维护方面，有相应的成熟的库redux和vuex，帮助开发者管理复杂应用的状态数据。

以太坊dapp开发框架truffle组件中有drizzle框架，基于redux开发，主要特点是能够负责同步合约和交易的状态。

由于以太坊交易需要若干个区块确认，drizzle负责处理新接收到的区块数据，分析是否有监听的合约或者交易的数据变化，有则同步到项目的store上。

本体链由于使用不同的共识算法，交易确认大体上在秒级，开发时无需处理不同区块数据，直到获取相关数据。

主要痛点是调用合约，发送交易。目前由本体社区提供的dapi.js和Chrome插件Cyano wallet能够很好解决dapp开发中这个痛点。我们已经有相关的demo项目（一元夺宝，token exchange）供开发者参考。 

### ontology dbox（名称暂定）

我们希望帮助开发者更好地上手dapp开发（web应用），计划推出基于ontology智能合约和主流前端框架的脚手架项目。该脚手架包含以下内容：

1. 命令行式交互式工具，通过npm安装。

2. 内置若干个demo，可以通过命令行方式下载，开发者可以基于demo项目开始自己的项目开发。该脚手架项目也可以接受其他开发者贡献demo。不限定UI框架和集成其他工具，依赖等。如集成ONTID，DDxF，cliam存证等。

   我们还提供了对应的文档库项目（即将上线）。接受开发者贡献其demo或脚手架对应的文档。

3. 内置智能合约测试框架。包括合约编译，部署，调用；支持多种网络选择（考虑对one click blockchian的支持扩展）。内置工具可以根据合约编译结果生成部署和调用的配置文件。可以对配置文件校验，修改。

4. 支持通过命令式发布到本体dapp仓库。

