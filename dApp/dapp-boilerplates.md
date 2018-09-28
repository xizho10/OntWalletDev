## Drizzle


#### 1.5.4. Drizzle

A collection of front-end libraries that make writing dapp front-ends easier and more predictable. The core of Drizzle is based on a Redux store, so you have access to the spectacular development tools around Redux. We take care of synchronizing your contract data, transaction data and more.

> Redux是一个用于应用程序状态管理的开源JavaScript库。

> Redux经常与React搭配运用，但其也可以独立使用。

> English Document: https://redux.js.org/

> 中文文档：http://www.redux.org.cn/




## 7. API

### 7.1. Web3.js

Web3.js is an Ethereum JavaScript API.

Just like we have geth, mist browser and so on to communicate with the ethereum node, there is also a javascript library called Web3.js which can be used to interact with a node. Since it is a javascript library, we can use it to build web based dapps.

### 7.2. Web3.py

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

### 7.3. web3j

web3j is a lightweight, highly modular, reactive, type safe Java and Android library for working with Smart Contracts and integrating with clients (nodes) on the Ethereum network:

![Alt text](https://raw.githubusercontent.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/web3jNetwork.png)

> https://web3j.io/

> https://github.com/web3j/web3j