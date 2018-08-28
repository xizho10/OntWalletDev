#dAPI简易dApp开发协议

dAPI是ontology去中心化App开发协议。

dApps使用者调用dAPI接口，通过dAPI provider和链通信，包括查询链信息、转账、Ontid等接口，

dAPI极大简化了sdk的复杂性，把构造交易、签名转移到dAPI provider。同时签名安全问题也转移到dAPI provider。

Cyano Wallet就是一个dAPI provider，当dApps发起确认请求时，Cyano Wallet会弹出确认框，只有用户确认后交易才发出。


dApps使用者调用dAPI接口，就可以通过dAPI provider和链通信，包括查询链信息、转账、Ontid等接口，优点是把dApps的安全问题转移到dAPI provider，dApps无需再关心安全问题。

dAPI provider


## 1. 账号和身份管理


账号和身份由dAPI provider管理，dApps用户无需直接管理私钥，就不需要签名交易。

当dApps发起签名请求，dAPI provider会通知用户授权。dAPI provider也可以把请求转移给第三方做授权，如用Ledger钱包做签名。


网络 api：
```

type Network = 'MAIN' | 'TEST' | 'PRIVATE';
type Asset = 'ont' | 'ong';

function getGenerateBlockTime(): Promise<number | null>
function getNodeCount(): Promise<number>
function getBlockHeight(): Promise<number>
function getMerkleProof(txHash: string): Promise<MerkleProof>
function getStorage(contract: string, key: string): Promise<string>
function getAllowance(asset: Asset, fromAddress: string, toAddress: string): Promise<BigNumber>
function getBlock(block: number | string): Promise<Block>
function getTransaction(txHash: string): Promise<Transaction>
function getNetwork(): Network
function getBalance(address: string): Promise<Balance>

```

## 2. 资产

获取dAPI provider里所有相关的账号
```
getOwnAccounts() : string[]
```


获取dAPI provider里的默认账号
```
function getDefaultAccount(): string | null
```


```sender``` 转账```amount```给```recipient```，``` asset```是资产名。```sender```必须在```getOwnAccounts```中存在。

```
function makeTransfer(sender: string, recipient: string, asset: Asset, amount: BigNumber): Promise<void>
```

## 数字身份

获取dAPI provider里所有相关的身份
```
getOwnIdentities() : string[]
```

获取dAPI provider里的默认的身份
```


function getDefaultIdentity(): string | null

```

查询身份

```
interface OntIdDDO {
    ...
}

function getDDO(ontId: string): Promise<OntIdDDO>

```

查询属性

```
interface OntIdAttribute {
    key: string;
    type: string;
    value: string;
}

function getAttributes(ontId: string): Promise<OntIdAttribute[]>

```

添加属性


```


function addAttributes(ontId: string, attributes: OntIdAttribute[]): Promise<void>

```


删除属性


```

function removeAttribute(ontId: string, key: string): Promise<void>

```

## 3. 数据签名

对数据hash做签名

```
function signMessageHash(messageHash: string, accountOrIdentity: string): Promise<string>
```

验证数据
```
function verifyMessageHash(messageHash: string, accountOrIdentity: string, signature: string): Promise<boolean>
```


对数据hash做

```
function signMessage(message: string, accountOrIdentity: string): Promise<string>
```

验证数据
```
function verifyMessage(message: string, accountOrIdentity: string, signature: string): Promise<boolean>
```

## 4. 智能合约


部署智能合约

```
function invokeRead(code: string, name: string, version: string, author: string, 
    email: string, description: string, needStorage: boolean, gasPrice: BigNumber, gasLimit: BigNumber): Promise<any>

```


调用智能合约

```
type ParameterType = 'Boolean' | 'Integer' | 'ByteArray' | 'Interface' | 'Array' | 'Struct' |
  'Map' | 'String' | 'Int' | 'Long' | 'IntArray' | 'LongArray' | 'Address';

interface Parameter {
    type: ParameterType;
    value: string;
}

function invoke(contract: string, method: string, parameters: Parameter[], 
  gasPrice: BigNumber, gasLimit: BigNumber): Promise<void>
  
```

预执行智能合约


```
function invokeRead(contract: string, method: string, parameters: Parameter[]): Promise<any>

```


监听智能合约


```
type EventListener = (data: any) => void;

function addEventListener(listener: EventListener): void

```

删除监听


```
function addEventListener(listener: EventListener): void

```


5. 架构图

OEP-6 架构图

![架构图](https://github.com/ontio/OEPs/blob/d0ec329aebcc324d47ccbc894b1f7f20f069d793/OEP-6/OEP-6-1.svg)