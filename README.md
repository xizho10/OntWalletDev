#  Ontology Obox Framework

对标[Ethereum Truffle](https://truffleframework.com/docs)，[Truffle调研报告](dApp/dapp.md).

dApp优势：
* 减轻节点故障。现代web应用程序依赖的基础设施，如服务器、代码库、数据库等，即使采用高可用性方案和可靠的基础设施服务商，也难以避免存在单点故障和停机。dapp通过多个对等节点网络上存储数据或基础架构的关键组建来缓解这些问题。
* 减少对中心机构的依赖。软件中的业务逻辑本质上是区块链上的一组智能合约。传统的软件业务逻辑和数据无法保证在服务器上不被篡改。智能合约无法被随意修改，数据在每个节点上都有记录，可以减少对中心化的依赖。
* 提高安全性。dApp可以对上链数据做保护或加密，用户通过密钥获取数据，无需通过数据网关。
* 密码学。账户安全性。
* 去中心化数据存储。多节点存储。

## video

[![Watch the video](https://img.youtube.com/vi/T-D1KVIuvjA/maxresdefault.jpg)](https://youtu.be/T-D1KVIuvjA)

[![Watch the video](https://img.youtube.com/vi/T-D1KVIuvjA/maxresdefault.jpg)](https://v.qq.com/x/page/u0784b610k9.html)

## Ontology Obox Framework

With obox you can:

* Blockchain(Ontology Node)
* Smart Contract
* Decentralized Storage (IPFS)
* Web Technologies

### Ontology Node

downloading the latest [Ontology release](https://github.com/ontio/ontology/releases) and starting it as below.
```
$ ./ontology --testmode 

```
需要开放具有UI功能的节点，类似Ganache。


### smart contract

* [smart contract automated testing framework](https://github.com/ontio-community/ontology-sctf) 
* [SmartX](http://smartx.ont.io/#/)
* [dapi](https://ontio.github.io/documentation/ontology_dapp_dev_tutorial_en.html)
* [SDKs](https://ontio.github.io/documentation/ontology_overview_sdks_en.html)

正在整合成一个框架，同时实现python 和typescript版本

### IPFS

* [IPFS实操手册](https://github.com/xizho10/IPFS-For-Chinese/blob/master/动手实践/IPFS实操手册.md)

实现用ts和python调用IPFS的demo



### Web Technologies

需要前端开发脚手架


## 进度


定鑫:
1. ontology-python-obox: unbox, init,deploy, invoke, compile, test  //test使用帅帅的测试框架，节省时间
2. ontology-python-debug //fork vm代码，基于vm上增加debug
3. ontology-python-obox: debug
4. ontology-python-obox: install SC
5. IPFS python 调用例子。

帅帅：
1. pythonsdk 支持python 3.6,    
2. python vm开发  
3. python vm debug测试
4. 除了obox，还有子链调研和开发

大双：
1. 开发基于ONT ID 的demo，使用Vue/React + Node.js + db
2. 开发基于claim存证的demo，使用Vue/React+ Nodejs + IPFS
3. dbox 基本命令实现
4. dbox智能合约测试框架集成
5. Mist provider类似实现
6. IPFS ts 调用例子。


## Punica

Punica Suite:The Ontology Blockchain dApp development framework。
Punica Box: 开发dapp的脚手架和例子。A set of boilerplates or examples to help developers quickly build distributed applications on the Ontology blockchain with Punica.
solo-chain: Ontology 的测试节点


Punica：
1. punica（智能合约的编译/部署/测试/debug命令行工具，punica-box下载和发布）。正在开发
2. solo-chain(具有ui的测试节点)。正在开发
3. punica-box（脚手架或dApp demo）。需要帮助
4. ui设计、文档、视频、演讲。需要帮助

Smartx：
1. debugger增加转换工具和测试框架功能。测试功能正在开发，其他已完成
2. debugger功能测试。需要帮助
3. 文档教程。需要帮助

https://github.com/punica-box

https://github.com/punicasuite
