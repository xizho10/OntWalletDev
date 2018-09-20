#  Ontology obox framework


## ethereum truffle framework


https://truffleframework.com/docs


* ganache
* truffle
* drizzle

## Ontology obox framework

With obox you can:

* Blockchain(Ontology Node)
* Smart Contract
* Decentralized Storage (IPFS)
* Web Technologies

### Ontology Node

downloading the latest [Ontology release](https://github.com/ontio/ontology/releases) and starting it as below.
```
$ ./ontology --testmode --gasprice 0

```

### smart contract

* [smart contract automated testing framework](https://github.com/ontio-community/ontology-sctf) 
* [SmartX](http://smartx.ont.io/#/)

### IPFS

https://github.com/ipfs/ipfs

https://github.com/ipfs/js-ipfs

https://github.com/ipfs/go-ipfs

**IPFS is a protocol**:

* defines a content-addressed file system
* coordinates content delivery
* combines Kademlia + BitTorrent + Git

**IPFS is a filesystem**:

* has directories and files
* mountable filesystem (via FUSE)

**IPFS is a web**:

* can be used to view documents like the web
* files accessible via HTTP at https://ipfs.io/<path>
* browsers or extensions can learn to use the ipfs:// URL or dweb:/ipfs/ URI schemes directly
* hash-addressed content guarantees authenticity

**IPFS is modular**:

* connection layer over any network protocol
* routing layer
* uses a routing layer DHT (kademlia/coral)
* uses a path-based naming service
* uses bittorrent-inspired block exchange

**IPFS uses crypto**:

* cryptographic-hash content addressing
* block-level deduplication
* file integrity + versioning
* filesystem-level encryption + signing support

**IPFS is p2p**:

* worldwide peer-to-peer file transfers
* completely decentralized architecture
* no central point of failure

**IPFS is a cdn**:

* add a file to the filesystem locally, and it's now available to the world
* caching-friendly (content-hash naming)
* bittorrent-based bandwidth distribution


**IPFS has a name service**:

IPNS, an SFS inspired name system
global namespace based on PKI
serves to build trust chains
compatible with other NSes
can map DNS, .onion, .bit, etc to IPNS





### Web Technologies

脚手架