<pre> 



 
  OEP: 6 



 
  Title: API for dApps (dAPI) and communication protocol for dAPI providers 



 
  Author: Matus Zamborsky <zamborsky@gmail.com> 



 
  Type: Standard 



 
  Status: Draft 



 
  Created: 2018-08-03 



 
</pre> 



 
 



 
==Abstract== 



 
 



 
This proposal has two major parts: 



 
 



 
* A Javascript API is proposed for dApps development. This dAPI allows dApps to communicate with Ontology blockchain and make requests for transfers, ONT ID registration and others, without requiring users to trust the dApp itself. The issue of trust is shifted to the dAPI provider. 



 
 



 
* A Communication protocol is proposed for dAPI provider development. This allows multiple Wallet implementators to offer the same unified service to users of dApps and prevent fragmentation of dApp development. 



 
 



 
==Motivation== 



 
 



 
Currently a dApp will use one of the SDKs (Typescript, Java, Python, ...) to communicate with Ontology network. This setup has three main disadvantages: 



 
 



 
1. User of the dApp will have to trust the dApp developer with his private keys and that information about transfers mediated through the dApp are legitimate. 



 
 



 
2. Although the SDKs are very powerful, they are hard to use. A more streamlined API will allow developers to focus on the application itself. 



 
 



 
3. Hard to implement integration to external signing mechanism (e.g.: Ledger, Trezor) 



 
 



 
==Specification== 



 
This proposal makes use of the following functions and definitions: 



 
 



 
*'''SDK''', a software development kit implementing low level communication with the network and providing high level interface for dApps. 



 
 



 
*'''dApp''', an application with decentralised characteristics running in web environment. The application uses Ontology network for value transfers, contracts enforcing and identification between participants. 



 
 



 
*'''dAPI''', the API for dApps this OEP is proposing. 



 
 



 
*'''dAPI provider''', an implementation of the dAPI in the form of web browser plugin or other means, where a user interaction with the provider can be injected into api call workflow (e.g.: confirming transfer). 



 
 



 
*'''Notify event''', an event broadcasted from smart contract execution. 



 
 



 
*'''NEOVM''', a lightweight virtual machine for execution of Neo/Ontology smart contracts. 



 
 



 
===Asynchronicity and error handling=== 



 
All the functions except '''Utils''' component are communicating with extension through asynchronious message channel. Therefore all the methods are returning Promises.  



 
 



 
The promises will be either resolved immediately if no interaction with user UI or blockchain is required or later when the user action takes place/blockchain responds. In case the call to method trigger an error, the error code is transmitted in rejected promise. Specific error codes are described with every method. 



 
 



 
===Account/Identity management=== 



 
Because dAPI shifts the issue of trust from dApp to dApp provider, all account and identity management is external to the dApp. Therefore there are no methods which directly handle private keys. The dApp won't need to sign the transaction itself.  



 
 



 
Any time dApp makes a call that requires a private key to sign something (makeTransfer, sign), dApp provider will inform user about the action and prompt him for permission. 



 
 



 
dApp provider can even forward the request to external signing mechanism as part of the process. This way the dApp does not need to specifically integrate with such mechanism. 



 
 



 
dAPI providers can choose to support multiple accounts and identities. Account and identity switching is part of dAPI provider implementation. dAPI provider should share with dApp as little information about user accounts and identities as possible, because it posses a security risk. Otherwise malicious dApp can list all user accounts with balances and identities. 



 
 



 
====dAPI access restriction==== 



 
Using dAPI any dApp is able to call the dAPI provider and initiate an interaction with the user (e.g.: <code>makeTransfer</code>). Only prerequisite is, that the user visits the dApp page. Although the user will need to confirm such an action, bothering him with this action, if he has no intention to confirm it, will hinder the experience. 



 
 



 
Therefore the dAPI will forward with every request the <code>Caller</code> object containing the <code>url</code> of the dApp page or <code>id</code> of another extension trying to communicate with dAPI provider. It is upto the dAPI provider to implement custom permission granting workflow or automatic blacklisting. 



 
 



 
<pre> 



 
interface Caller { 



 
  url?: string; 



 
  id?: string; 



 
} 



 
</pre> 



 
 



 
===Encoding=== 



 
The interaction with dAPI often requires specification of '''Address''', '''Identity''', '''Contract address''' or '''Public Key'''. Those concepts are represented by string representation with specific encodings. 



 
 



 
====Address==== 



 
* 34 bytes long 



 
* using Base58 check encoding 



 
* starts with A letter 



 
 



 
====Contract address==== 



 
* 40 bytes long 



 
* using Hex encoding 



 
 



 
====Identity==== 



 
* 42 bytes long 



 
* using Base58 check encoding for 34 byte suffix 



 
* starts with 'did:ont:' prefix 



 
 



 
====Public Key==== 



 
* 33/35 bytes long 



 
* using Hex encoding 



 
 



 
===Complex structures=== 



 
API specification is a complex document. Every method has some inputs and outputs. Although we use the primitive types (numbers, strings, booleans) whenever possible, there are places where a complex object is required. To precisely describe the structure of those objects, we'd chosen Typescript syntax. 



 
 



 
===Components=== 



 
Although this proposal is bringing clear and simple API for the dApps, the individual functions can be divided into these components: 



 
 



 
* '''Network''', a thin wrapper around the Ontology Node API, masking the complexity of rpc/rest calls and web-sockets with Request-Response facade. 



 
 



 
* '''Provider''', functions for getting information about dAPI provider 



 
 



 
* '''Asset''', functions for transferring assets between user account and others. 



 
 



 
* '''Identity''', functions for interacting with own ONT-ID identity. 



 
 



 
* '''SmartContract''', a high level wrapper around the Smart Contract invocation and deployment. 



 
 



 
* '''Message''', functions for signing arbitrary messages. 



 
 



 
* '''Utils''', a group of utility function for encoding and decoding the data from/to blockchain. 



 
 



 
===Network=== 



 
A network API consists of: 



 
 



 
<pre> 



 
type NetworkType = 'MAIN' | 'TEST' | 'PRIVATE'; 



 
type Asset = 'ONT' | 'ONG'; 



 
 



 
interface Network { 
  type: NetworkType; 
  address: string; 
} 



 
 



 
function getGenerateBlockTime(): Promise<number | null> 



 
function getNodeCount(): Promise<number> 



 
function getBlockHeight(): Promise<number> 



 
function getMerkleProof(txHash: string): Promise<MerkleProof> 



 
function getStorage(contract: string, key: string): Promise<string> 



 
function getAllowance(asset: Asset, fromAddress: string, toAddress: string): Promise<number> 



 
function getBlock(block: number | string): Promise<Block> 



 
function getTransaction(txHash: string): Promise<Transaction> 



 
function getNetwork(): Network 



 
function getBalance(address: string): Promise<Balance> 



 
</pre> 



 
 



 
For further explanation about the wrapped method consult https://ontio.github.io/documentation/restful_api_en.html . The types '''Transaction''', '''Block''', '''MerkleProof''' and '''Balance''' corresponds to the exact object returned from Ontology blockchain. 