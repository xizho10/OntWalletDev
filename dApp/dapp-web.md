## parity/MIST/State of Dapps


#### parity介绍

parity主界面

该界面主要展示了parity支持的功能

![avatar](https://github.com/lucas7788/workingdata/blob/master/blockchaingames/ethereum/parity1.png)

节点信息界面

![avatar](https://github.com/lucas7788/workingdata/blob/master/blockchaingames/ethereum/parity2.png)

dapp 浏览器界面

![avatar](https://github.com/lucas7788/workingdata/blob/master/blockchaingames/ethereum/parity3.png)

web3 console界面

![avatar](https://github.com/lucas7788/workingdata/blob/master/blockchaingames/ethereum/paritycli.png)

交易队列界面

![avatar](https://github.com/lucas7788/workingdata/blob/master/blockchaingames/ethereum/paritytxqueue.png)



### 1.3. MIST

The Mist browser is the tool of choice to browse and use Ðapps.

> https://github.com/ethereum/mist

![Alt text](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/mistGeth.png)

The Mist is a desktop application used to communicate with your node. Anything we can do using the geth console can be accomplished through this Graphical User Interface.

#### 1.3.1. Install

<div align=center><img height="300" src="https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/installMist1.png"/></div>

<div align=center><img height="300" src="https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/installMist2.png"/></div>

<div align=center><img height="300" src="https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/installMist3.png"/></div>

<div align=center><img height="300" src="https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/installMist4.png"/></div>

#### 1.3.2. Usage

![Alt text](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/useMist0.png)

![Alt text](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/useMist1.png)

![Alt text](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/useMist2.png)

![Alt text](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/useMist3.png)

ÐApps are ranked by DAU (daily active users).

Dapp categories:

- Games
- Gambling
- Social
- Finance
- Exchanges
- Development
- Media
- Wallet
- Storage
- Security
- Property
- Governance
- Identity
- Energy
- Insurance
- Health

![Alt text](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/useMist4.png)

![Alt text](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/useMist5.png)

![Alt text](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/useMist6.png)

![Alt text](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/useMist7.png)

![Alt text](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/useMist8.png)

![Alt text](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/useMist9.png)



#### 1.3.4. Mist API

Mist provides an API for dapp developers to use special features only available in Mist.

> https://github.com/ethereum/mist/blob/develop/MISTAPI.md

we can check for the mist object in our dapp:

```js
if (typeof mist !== 'undefined') {
    ...
}
```

we can use mist's provider:

```js
if (typeof web3 !== 'undefined') {
  web3 = new Web3(web3.currentProvider);
} else {
  web3 = new Web3('ws://localhost:8546');
}
```

1. **Mist API Example: mist.platform**

Returns the current platform, mist is running on:

- `darwin` (Mac OSX)
- `win32` (Windows)
- `linux` (Linux)

2. **Mist API Example: mist.requestAccount(callback)**

Asks the user to provide, or create a new account.

`Function` The callback to be called with the new address as the second parameter.

```js
mist.requestAccount(function(error, address) {
  console.log('Added new account', address);
});
```




## 9. State of Dapps

![stateDapps](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/stateDapps.png)

> https://www.stateofthedapps.com/

## 10. The Dapp Daily

Ethereum ecosystem updates from [Sourcerers](https://sourcerers.io/).

![Sourcerers](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/sourceres.png)

![dappDaily1](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/dappDaily1.png)

![dappDaily2](https://github.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/dappDaily2.png)

