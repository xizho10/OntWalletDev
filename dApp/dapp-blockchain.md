## Geth/Ganache



#### 1.5.3. Ganache

one click blockchain.

Ganache is a personal blockchain for Ethereum development you can use to deploy contracts, develop your applications, and run tests. It is available as both a desktop application as well as a command-line tool (formerly known as the TestRPC). Ganache is available for Windows, Mac, and Linux.

![ganacheBlocks1](https://raw.githubusercontent.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/ganacheBlocks1.png)

![ganacheBlocks2](https://raw.githubusercontent.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/ganacheBlocks2.png)

![ganacheBlocks3](https://raw.githubusercontent.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/ganacheBlocks3.png)

![ganacgeMetaMask1](https://raw.githubusercontent.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/ganacgeMetaMask1.png)

![ganacgeMetaMask2](https://raw.githubusercontent.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/ganacgeMetaMask2.png)

![ganacgeMetaMask3](https://raw.githubusercontent.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/ganacgeMetaMask3.png)

![ganacgeMetaMask4](https://raw.githubusercontent.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/ganacgeMetaMask4.png)

![ganacgeMetaMask5](https://raw.githubusercontent.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/ganacgeMetaMask5.png)




## 8. Technology

### 8.1. ENS

Ethereum Naming System is the DNS for the Ethereum world. Just like you map an IP address to a human readable name, you can map any Ethereum contract or wallet address to a human readable name.

Ex: `146.115.22.177` → `google.com`. Instead of typing the ip address in your browser, you type google.com which resolves to that IP address

Ex: `0x80C013d980aB049471c88E1603b8b4a60E03295C` is my wallet address. If you are in the mood to send me some Ether, you don’t have to memorize this address. Once ENS launches, I will probably map it to `mvmurthy.eth` and you can use that to send me money easily.

> https://ens.domains/

> Docs: https://docs.ens.domains/en/latest/

![ens](https://raw.githubusercontent.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/ens.png)

![getStartedEns](https://raw.githubusercontent.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/getStartedEns.png)

![ensSubDomains1](https://raw.githubusercontent.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/ensSubDomains1.png)

![ensSubDomains2](https://raw.githubusercontent.comwdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/ensSubDomains2.png)

### 8.2. Swarm

The blockchain is good to store small amounts of data. What if you want to store a patient record, a sale deed or some large file which needs to be publicly timestamped? It is expensive and also not scalable to store a blob in the blockchain.

Swarm is used to solve this problem. Swarm is a decentralized content storage and distribution service. You can think of it as a CDN but instead of the entire CDN hosted on one company’s servers, it is distributed on computers across the internet. Just like you run an Ethereum node, you run a swarm node to connect to the swarm network.

![swarmHelp](https://raw.githubusercontent.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/swarmHelp.png)

When you deploy an Ethereum contract on to the blockchain, you get a deployed address and JSON interface of the ABI (The contract interface similar to API).

When you want someone to use your contract, you have to give them the deployed address and the ABI. In the future, the ABI will be stored on Swarm so anyone can look up the ABI just by looking at the Ethereum address.

![Swarm](https://raw.githubusercontent.com/wdx7266/learning-ethereum/tree/master/img/DApp/Ethereum/swarm.png)

Swarm is a distributed storage platform and content distribution service, a native base layer service of the ethereum web3 stack. The primary objective of Swarm is to provide a decentralized and redundant store for dapp code and data as well as block chain and state data.

Swarm is also set out to provide various base layer services for web3, including node-to-node messaging, media streaming, decentralised database services and scalable state-channel infrastructure for decentralised service economies.

> http://swarm-gateways.net/bzz:/theswarm.eth/

- Fault Tolerant: Redundant storage (local replication and erasure coding ensures data availability even in the face of node dropouts or data loss).

- Censorship Resistant: Sites cannot be 'taken down'(data is stored throughout the network without vulnerable central hubs).

- DDoS Resistant: Fully decentralised peer-to-peer network is more resilient against DDoS than any centralised system.

- Zero Downtime: Redundancy ensures that the network continues to deliver data even when individual nodes go offline.

- Self-sustaining: Built-in incentive system ensures the network's economic viability.

### 8.3. IPFS

IPFS (Inter Planetary File System) is conceptually exactly similar to Swarm. It is a decentralized storage system. It is not related to Ethereum directly but can be integrated with Ethereum.

> https://ipfs.io/

The differences between Swarm and IPFS here: [IPFS & SWARM](https://github.com/ethersphere/go-ethereum/wiki/IPFS-&-SWARM).

### 8.4. Whisper

Whisper is an interesting technology in the Ethereum ecosystem. It is a communication protocol for Dapps to interact with one another.

> https://github.com/ethereum/wiki/wiki/Whisper

- DApps that need to publish small amounts of information to each other and have the publication last some substantial amount of time. For example, a currency exchange DApp may use it to record an offer to sell some currency at a particular rate on an exchange. In this case, it may last anything between tens of minutes and days. The offer wouldn't be binding, merely a hint to get a potential deal started (DApps需要相互发布少量信息并使所发布的信息持续相当长的时间。例如，货币兑换DApp可以使用它来记录在交易所以特定汇率出售某种货币的申请。在这种情况下，它可能持续几十分钟到几天之间的任何事情。这个申请不具有约束力，只是暗示可能会有一笔交易开始).

- DApps that need to signal to each other in order to ultimately collaborate on a transaction. For example, a currency exchange DApp may use it to coordinate an offer prior to creating one (or two, depending on how the exchange is structured) transactions on the exchange (需要相互发信号以便最终在交易上进行协作的DApp。例如，货币兑换DApp可以在交易所创建一个或者两个（取决于交易所的结构）交易之前使用它来协调出价).

- DApps that need to provide non-real-time hinting or general communications between each other. E.g. a small chat-room app (需要在彼此之间提供非实时提示或一般通信的DApp。例如。一个小聊天室应用程序).

- DApps that need to provide dark (plausible denial over perfect network traffic analysis) comms to two correspondents that know nothing of each other but a hash. This could be a DApp for a whistleblower to communicate to a known journalist exchange some small amount of verifiable material and arrange between themselves for some other protocol (Swarm, perhaps) to handle the bulk transfer (DApps需要为通向双方提供茫然通信（合理拒绝网络流量分析）——彼此一无所知，只有哈希。这可能是一个DApp，用于举报人与已知的记者交流一些少量可验证的材料，并在他们自己之间安排一些其他协议（可能是Swarm）来处理批量转移).
