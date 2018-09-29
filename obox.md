#  Ontology obox framework

对标Ethereum truffle framework，https://truffleframework.com/docs


## Ontology obox framework

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

### smart contract

* [smart contract automated testing framework](https://github.com/ontio-community/ontology-sctf) 
* [SmartX](http://smartx.ont.io/#/)
* dapi
* SDKs

### IPFS

* [IPFS实操手册](https://github.com/xizho10/IPFS-For-Chinese/blob/master/动手实践/IPFS实操手册.md)





### Web Technologies

开发脚手架


## 进度


定鑫:
1. ontology-python-obox: unbox, init,deploy, invoke, compile, test  //test使用帅帅的测试框架，节省时间
2. ontology-python-debug //fork vm代码，基于vm上增加debug
3. ontology-python-obox: debug
4. ontology-python-obox: install SC
5. IPFS python sdk调用。

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