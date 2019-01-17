# DMA项目基础模块方法调用

----------

## 一、 Asset模块方调用（AssetBaseService）

----------

### 1.创建合约

方法名 ：`deploy()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _name | String  |合约名称|
| _symbol | String  |合约简称|
| _metadata | String  |合约信息|
| _isBurn | boolean  |合约是否可销毁|

返回值类型：`String`
返回说明：合约地址

### 2. 获取ERC721合约名称

方法名 ：`name()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|

返回值类型：`String`
返回说明：合约名称

### 3. 获取合约符号

方法名 ：`symbol()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|

返回值类型：`String`
返回说明：合约符号

### 4. 合约拥有者地址

方法名 ：`owner()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|

返回值类型：`String`
返回说明：合约拥有者地址

### 5. 根据地址查询资产数量

方法名 ：`balanceOf()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| owner | String  | 拥有者地址|

返回值类型：`String`
返回说明：合约拥有者地址

### 6. 根据地址获取所以tokenId

方法名 ：`tokenIds()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| owner | String  | 拥有者地址|

返回值类型：`List<BigInteger>`
返回说明：tokenId数组

### 7. 根据tokenid查询拥有者地址

方法名 ：`ownerOf()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| tokenId | BigInteger  | tokenId|

返回值类型：`String`
返回说明：拥有者地址

### 8.根据tokenid查询token单元数据信息

方法名 ：`getTokenData()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| tokenId | BigInteger  | tokenId|

返回值类型：`String`
返回说明：token单元数据信息

### 9.根据tokenid查询token详情

方法名 ：`getTokenInfo()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| tokenId | BigInteger  | tokenId|

返回值类型：`TokenInfoDto`
返回说明：token信息

```
String owner;//拥有者
Boolean isTransfer;//是否可转移
Boolean isBurn;//是否可销毁
String data;//token信息
BigInteger status;//token状态
String user;//用户信息

```

### 10.获取合约详情

方法名 ：`getContractInfo()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|

返回值类型：`ContractInfoDto`
返回说明：合约信息

```
String name;//合约名称
String symbol;//合约符号
String metadata;//合约信息
String owner;//合约拥有者
boolean isBurn;//合约是否可销毁
```

### 11.根据tokenid查询token状态

方法名 ：`getTokenStatus()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| tokenId | BigInteger  | tokenId|

返回值类型：`BigInteger`
返回说明：token状态值

### 12.根据tokenid查询user信息

方法名 ：`getTokenUser()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| tokenId | BigInteger  | tokenId|

返回值类型：`String`
返回说明：token user信息

### 13.判定是否为合约代理人

方法名 ：`isOperator()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| _owner | String  | 合约拥有者地址|
| _operator | String  | 代理人地址|

返回值类型：`Boolean`
返回说明：true 是合约代理人；false 不是合约代理人

### 14.根据tokenid查询token是否可转移

方法名 ：`getTokenIsTransfer()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| tokenId | BigInteger  | tokenId|

返回值类型：`Boolean`
返回说明：true 可转移；false 不可转移

### 15.获取合约单元数据

方法名 ：`getContractData()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|

返回值类型：`String`
返回说明：合约单元数据

### 16.获取token发行量

方法名 ：`totalSupply()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|

返回值类型：`BigInteger`
返回说明：token发行量

### 17.根据tokenid获取授权地址

方法名 ：`getApproved()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| tokenId | BigInteger  | tokenId|

返回值类型：`String`
返回说明：授权地址

### 18.创建token

####    1.创建token返回交易hash

#####   (1).创建单个token

方法名 ：`mint()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _to | String  | token归属者地址|
| _info | String  | token信息|
| tokenid | BigInteger  | tokenId|
| _isTransfer | boolean  | 该token是否可转移|
| _isBurn | boolean  | 该token是否可销毁|

返回值类型：`String`
返回说明：直接返回交易hash，不等待交易结果

#####   (2).根据类型tokenid批量创建token

方法名 ：`mintMulti()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _to | String  | token归属者地址|
| _info | String  | token信息|
| tokenid | BigInteger  | 首tokenId，之后产生的tokenid在此基础上进行累加|
| count | BigInteger  | 创建数量|
| _isTransfer | boolean  | 该token是否可转移|
| _isBurn | boolean  | 该token是否可销毁|

返回值类型：`String`
返回说明：直接返回交易hash，不等待交易结果

####    2.创建token返回交易信息

#####   (1).创建单个token

方法名 ：`mintReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _to | String  | token归属者地址|
| _info | String  | token信息|
| tokenid | BigInteger  | tokenId|
| _isTransfer | boolean  | 该token是否可转移|
| _isBurn | boolean  | 该token是否可销毁|

返回值类型：`TransactionReceipt`
返回说明：等待返回交易结果

```
{
	"blockHash": "0x159c800aaf75a7d95b63336be18fd3bf49dc6531090b2c8b420940fdd8e155a7", //块hash
	"blockNumber": 4830791,//块号
	"blockNumberRaw": "0x49b647",
	"cumulativeGasUsed": 1310953,
	"cumulativeGasUsedRaw": "0x1400e9",
	"from": "0x0b23eff3a9d8f02829d3b0714cf2e00f5fae2b47",//发起方地址
	"gasUsed": 214691,
	"gasUsedRaw": "0x346a3",
	"logs": [{
		"address": "0xba216d39d89be5da10eec33c17ed522ab8955b93",
		"blockHash": "0x159c800aaf75a7d95b63336be18fd3bf49dc6531090b2c8b420940fdd8e155a7",
		"blockNumber": 4830791,
		"blockNumberRaw": "0x49b647",
		"data": "0x",
		"logIndex": 4,
		"logIndexRaw": "0x4",
		"removed": false,
		"topics": ["0xddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef", "0x0000000000000000000000000000000000000000000000000000000000000000", "0x000000000000000000000000edf05c600ad3be116060cc5e982d5d28aef9892e", "0x000000000000000000000000000000000000000000000000000000000000000c"],
		"transactionHash": "0x0245e9aa1b13eb11e4d8cef9b679622a157520501336da5ae548cb8cbfa4ff8d",
		"transactionIndex": 28,
		"transactionIndexRaw": "0x1c"
	}],
	"logsBloom": "0x00000000000000000000000000000000000002000000000000000000000000000000000000000200000000000000000000000000000000000000000000000000000000000000000000000008000000100000000000000000000000000000000010000000020000000000000000000800000000000000000000000010000000000000000000000000000000000000000000000000000000000000000000000000020000000000000000000000000000000000000000000000000000001000004000000002000000000000000000000020000000000000000000000000000020200000000000000000000000000000000000000000000000000000000000000000",
	"status": "0x1",//交易状态
	"to": "0xba216d39d89be5da10eec33c17ed522ab8955b93",//接收方地址
	"transactionHash": "0x0245e9aa1b13eb11e4d8cef9b679622a157520501336da5ae548cb8cbfa4ff8d",//交易hash
	"transactionIndex": 28,
	"transactionIndexRaw": "0x1c"
}
```  

#####   (2).根据类型tokenid批量创建token

方法名 ：`mintMultiReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _to | String  | token归属者地址|
| _info | String  | token信息|
| tokenid | BigInteger  | 首tokenId，之后产生的tokenid在此基础上进行累加|
| count | BigInteger  | 创建数量|
| _isTransfer | boolean  | 该token是否可转移|
| _isBurn | boolean  | 该token是否可销毁|

返回值类型：`TransactionReceipt`
返回说明：等待返回交易结果

```
{
	"blockHash": "0x159c800aaf75a7d95b63336be18fd3bf49dc6531090b2c8b420940fdd8e155a7", //块hash
	"blockNumber": 4830791,//块号
	"blockNumberRaw": "0x49b647",
	"cumulativeGasUsed": 1310953,
	"cumulativeGasUsedRaw": "0x1400e9",
	"from": "0x0b23eff3a9d8f02829d3b0714cf2e00f5fae2b47",//发起方地址
	"gasUsed": 214691,
	"gasUsedRaw": "0x346a3",
	"logs": [{
		"address": "0xba216d39d89be5da10eec33c17ed522ab8955b93",
		"blockHash": "0x159c800aaf75a7d95b63336be18fd3bf49dc6531090b2c8b420940fdd8e155a7",
		"blockNumber": 4830791,
		"blockNumberRaw": "0x49b647",
		"data": "0x",
		"logIndex": 4,
		"logIndexRaw": "0x4",
		"removed": false,
		"topics": ["0xddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef", "0x0000000000000000000000000000000000000000000000000000000000000000", "0x000000000000000000000000edf05c600ad3be116060cc5e982d5d28aef9892e", "0x000000000000000000000000000000000000000000000000000000000000000c"],
		"transactionHash": "0x0245e9aa1b13eb11e4d8cef9b679622a157520501336da5ae548cb8cbfa4ff8d",
		"transactionIndex": 28,
		"transactionIndexRaw": "0x1c"
	}],
	"logsBloom": "0x00000000000000000000000000000000000002000000000000000000000000000000000000000200000000000000000000000000000000000000000000000000000000000000000000000008000000100000000000000000000000000000000010000000020000000000000000000800000000000000000000000010000000000000000000000000000000000000000000000000000000000000000000000000020000000000000000000000000000000000000000000000000000001000004000000002000000000000000000000020000000000000000000000000000020200000000000000000000000000000000000000000000000000000000000000000",
	"status": "0x1",//交易状态
	"to": "0xba216d39d89be5da10eec33c17ed522ab8955b93",//接收方地址
	"transactionHash": "0x0245e9aa1b13eb11e4d8cef9b679622a157520501336da5ae548cb8cbfa4ff8d",//交易hash
	"transactionIndex": 28,
	"transactionIndexRaw": "0x1c"
}
```  

### 19.授权

####    1.授权，返回交易hash

#####   (1).对单个token进行授权

方法名 ：`approve()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _to | String  | 授权地址|
| tokenid | BigInteger  | tokenid|

返回值类型：`String`
返回说明：直接返回交易hash，不等待交易结果

#####   (2).以类型tokenid进行批量授权

方法名 ：`approveMulti()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _to | String  | 授权地址|
| tokenid | BigInteger  | 首tokenId，之后产生的tokenid在此基础上进行累加|
| count | BigInteger  | 创建数量|

返回值类型：`String`
返回说明：直接返回交易hash，不等待交易结果

#####   (3).以tokenid数组进行批量授权

方法名 ：`approveWithAarry()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _to | String  | 授权地址|
|  tokenids | List  | tokenid数组|

返回值类型：`String`
返回说明：直接返回交易hash，不等待交易结果

####    2.授权，返回交易信息

#####   (1).对单个token进行授权

方法名 ：`approveReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _to | String  | 授权地址|
| tokenid | BigInteger  | tokenid|

返回值类型：`TransactionReceipt`
返回说明：等待返回交易结果

```
{
	"blockHash": "0x159c800aaf75a7d95b63336be18fd3bf49dc6531090b2c8b420940fdd8e155a7", //块hash
	"blockNumber": 4830791,//块号
	"blockNumberRaw": "0x49b647",
	"cumulativeGasUsed": 1310953,
	"cumulativeGasUsedRaw": "0x1400e9",
	"from": "0x0b23eff3a9d8f02829d3b0714cf2e00f5fae2b47",//发起方地址
	"gasUsed": 214691,
	"gasUsedRaw": "0x346a3",
	"logs": [{
		"address": "0xba216d39d89be5da10eec33c17ed522ab8955b93",
		"blockHash": "0x159c800aaf75a7d95b63336be18fd3bf49dc6531090b2c8b420940fdd8e155a7",
		"blockNumber": 4830791,
		"blockNumberRaw": "0x49b647",
		"data": "0x",
		"logIndex": 4,
		"logIndexRaw": "0x4",
		"removed": false,
		"topics": ["0xddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef", "0x0000000000000000000000000000000000000000000000000000000000000000", "0x000000000000000000000000edf05c600ad3be116060cc5e982d5d28aef9892e", "0x000000000000000000000000000000000000000000000000000000000000000c"],
		"transactionHash": "0x0245e9aa1b13eb11e4d8cef9b679622a157520501336da5ae548cb8cbfa4ff8d",
		"transactionIndex": 28,
		"transactionIndexRaw": "0x1c"
	}],
	"logsBloom": "0x00000000000000000000000000000000000002000000000000000000000000000000000000000200000000000000000000000000000000000000000000000000000000000000000000000008000000100000000000000000000000000000000010000000020000000000000000000800000000000000000000000010000000000000000000000000000000000000000000000000000000000000000000000000020000000000000000000000000000000000000000000000000000001000004000000002000000000000000000000020000000000000000000000000000020200000000000000000000000000000000000000000000000000000000000000000",
	"status": "0x1",//交易状态
	"to": "0xba216d39d89be5da10eec33c17ed522ab8955b93",//接收方地址
	"transactionHash": "0x0245e9aa1b13eb11e4d8cef9b679622a157520501336da5ae548cb8cbfa4ff8d",//交易hash
	"transactionIndex": 28,
	"transactionIndexRaw": "0x1c"
}
``` 

#####   (2).以类型tokenid进行批量授权

方法名 ：`approveMultiReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _to | String  | 授权地址|
| tokenid | BigInteger  | 首tokenId，之后产生的tokenid在此基础上进行累加|
| count | BigInteger  | 创建数量|

返回值类型：`TransactionReceipt`
返回说明：等待返回交易结果

```
{
	"blockHash": "0x159c800aaf75a7d95b63336be18fd3bf49dc6531090b2c8b420940fdd8e155a7", //块hash
	"blockNumber": 4830791,//块号
	"blockNumberRaw": "0x49b647",
	"cumulativeGasUsed": 1310953,
	"cumulativeGasUsedRaw": "0x1400e9",
	"from": "0x0b23eff3a9d8f02829d3b0714cf2e00f5fae2b47",//发起方地址
	"gasUsed": 214691,
	"gasUsedRaw": "0x346a3",
	"logs": [{
		"address": "0xba216d39d89be5da10eec33c17ed522ab8955b93",
		"blockHash": "0x159c800aaf75a7d95b63336be18fd3bf49dc6531090b2c8b420940fdd8e155a7",
		"blockNumber": 4830791,
		"blockNumberRaw": "0x49b647",
		"data": "0x",
		"logIndex": 4,
		"logIndexRaw": "0x4",
		"removed": false,
		"topics": ["0xddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef", "0x0000000000000000000000000000000000000000000000000000000000000000", "0x000000000000000000000000edf05c600ad3be116060cc5e982d5d28aef9892e", "0x000000000000000000000000000000000000000000000000000000000000000c"],
		"transactionHash": "0x0245e9aa1b13eb11e4d8cef9b679622a157520501336da5ae548cb8cbfa4ff8d",
		"transactionIndex": 28,
		"transactionIndexRaw": "0x1c"
	}],
	"logsBloom": "0x00000000000000000000000000000000000002000000000000000000000000000000000000000200000000000000000000000000000000000000000000000000000000000000000000000008000000100000000000000000000000000000000010000000020000000000000000000800000000000000000000000010000000000000000000000000000000000000000000000000000000000000000000000000020000000000000000000000000000000000000000000000000000001000004000000002000000000000000000000020000000000000000000000000000020200000000000000000000000000000000000000000000000000000000000000000",
	"status": "0x1",//交易状态
	"to": "0xba216d39d89be5da10eec33c17ed522ab8955b93",//接收方地址
	"transactionHash": "0x0245e9aa1b13eb11e4d8cef9b679622a157520501336da5ae548cb8cbfa4ff8d",//交易hash
	"transactionIndex": 28,
	"transactionIndexRaw": "0x1c"
}
``` 

#####   (3).以tokenid数组进行批量授权

方法名 ：`approveWithAarryReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _to | String  | 授权地址|
|  tokenids | List  | tokenid数组|

返回值类型：`TransactionReceipt`
返回说明：等待返回交易结果
 
### 20.解除授权

####    1.解除授权，返回交易hash

#####   (1).解除单个token授权

方法名 ：`revokeApprove()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
|  tokenid | BigInteger  | tokenid|

返回值类型：`String`
返回说明：直接返回交易hash，不等待交易结果

#####   (2).以类型tokenid方式批量解除授权

方法名 ：`removeMultiApprove()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| tokenid | BigInteger  | 首tokenId，之后产生的tokenid在此基础上进行累加|
| count | BigInteger  | 创建数量|

返回值类型：`String`
返回说明：直接返回交易hash，不等待交易结果

#####   (3).以tokenid数组方式批量解除授权

方法名 ：`removeApproveWithArray()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| tokenids | List  |tokenid数组|

返回值类型：`String`
返回说明：直接返回交易hash，不等待交易结果

####    2.解除授权，返回交易信息

#####   (1).解除单个token授权

方法名 ：`revokeApproveReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
|  tokenid | BigInteger  | tokenid|

返回值类型：`TransactionReceipt`
返回说明：等待返回交易结果

#####   (2).以类型tokenid方式批量解除授权

方法名 ：`removeMultiApproveReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| tokenid | BigInteger  | 首tokenId，之后产生的tokenid在此基础上进行累加|
| count | BigInteger  | 创建数量|

返回值类型：`TransactionReceipt`
返回说明：等待返回交易结果

#####   (3).以tokenid数组方式批量解除授权

方法名 ：`removeApproveWithArrayReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| tokenids | List  |tokenid数组|

返回值类型：`TransactionReceipt`
返回说明：等待返回交易结果

### 21.转移token，返回交易hash

####    1.转移token，返回交易hash

#####   (1).转移单个token

方法名 ：`transfer()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _to | String  |接收者地址|
| tokenid | BigInteger  |tokenid|

返回值类型：`String`
返回说明：直接返回交易hash，不等待交易结果

#####   (2).以tokenid数组方式批量转移token

方法名 ：`transferWithAarry()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _to | String  |接收者地址|
| tokenids | List  |tokenid数组|

返回值类型：`String`
返回说明：直接返回交易hash，不等待交易结果

####    2.转移token，返回交易信息

#####   (1).转移单个token

方法名 ：`transferReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _to | String  |接收者地址|
| tokenid | BigInteger  |tokenid|

返回值类型：`TransactionReceipt`
返回说明：等待返回交易结果

#####   (2).以tokenid数组方式批量转移token

方法名 ：`transferWithAarryReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _to | String  |接收者地址|
| tokenids | List  |tokenid数组|

返回值类型：`TransactionReceipt`
返回说明：等待返回交易结果

### 22.销毁token

####    1.销毁token返回交易hash

方法名 ：`burn()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _owner | String  |拥有者地址|
| tokenid | BigInteger  |tokenid|

返回值类型：`String`
返回说明：直接返回交易hash，不等待交易结果

####    2.销毁token，返回交易信息

方法名 ：`burnReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _owner | String  |拥有者地址|
| tokenid | BigInteger  |tokenid|

返回值类型：`TransactionReceipt`
返回说明：等待返回交易结果

### 23.检查tokenid是否有效

方法名 ：`valid()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| tokenid | BigInteger  |tokenid|

返回值类型：`boolean`
返回说明：true 表示tokenid有效，false 表示tokenid无效

### 24.设置token转移状态

####    1.设置token转移状态，返回交易hash

方法名 ：`setIsTransfer()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| tokenid | BigInteger  |tokenid|
| _istransfer | boolean  |转移状态|

返回值类型：`String`
返回说明：直接返回交易hash，不等待交易结果

####    2.设置token转移状态，返回交易信息

方法名 ：`setIsTransferReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| tokenid | BigInteger  |tokenid|
| _istransfer | boolean  |转移状态|

返回值类型：`TransactionReceipt`
返回说明：等待返回交易结果

### 25.设置token状态值

####    1.设置token状态值，返回交易hash

方法名 ：`setStatus()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| tokenid | BigInteger  |tokenid|
| status | BigInteger  |状态值|

返回值类型：`String`
返回说明：直接返回交易hash，不等待交易结果

####    2.设置token状态值，返回交易信息

方法名 ：`setStatusReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| tokenid | BigInteger  |tokenid|
| status | BigInteger  |状态值|

返回值类型：`TransactionReceipt`
返回说明：等待返回交易结果

### 26.设置token user值

####    1.设置token user值，返回交易hash

方法名 ：`setUser()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| tokenid | BigInteger  |tokenid|
| user | String  |user信息|

返回值类型：`String`
返回说明：直接返回交易hash，不等待交易结果

####    2.设置token user值，返回交易信息

方法名 ：`setUserReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| tokenid | BigInteger  |tokenid|
| user | String  |user信息|

返回值类型：`TransactionReceipt`
返回说明：等待返回交易结果

### 27.设置合约代理人

####    1.设置合约代理人，返回交易hash

方法名 ：`setOperator()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _operator | String  |代理人地址|
| _isApproved | Boolean  |是否设为代理人|

返回值类型：`String`
返回说明：直接返回交易hash，不等待交易结果

####    2.设置合约代理人，返回交易信息

方法名 ：`setOperatorReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _operator | String  |代理人地址|
| _isApproved | Boolean  |是否设为代理人|

返回值类型：`TransactionReceipt`
返回说明：等待返回交易结果

### 28.设置合约单元数据

####    1.设置合约单元数据，返回交易hash

方法名 ：`setContractData()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| data | String  |单元数据|

返回值类型：`String`
返回说明：直接返回交易hash，不等待交易结果

####    2.设置合约单元数据，返回交易信息

方法名 ：`setContractDataReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| data | String  |单元数据|

返回值类型：`TransactionReceipt`
返回说明：等待返回交易结果

### 29.转让合约

####    1.转让合约，返回交易hash

方法名 ：`transferContract()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _newOwner | String  |合约接收者|

返回值类型：`String`
返回说明：直接返回交易hash，不等待交易结果

####    2.转让合约人，返回交易信息

方法名 ：`transferContractReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|
| _newOwner | String  |合约接收者|

返回值类型：`TransactionReceipt`
返回说明：等待返回交易结果


### 30.销毁合约

####    1.销毁合约，返回交易hash

方法名 ：`kill()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|

返回值类型：`String`
返回说明：直接返回交易hash，不等待交易结果

####    2.销毁合约，返回交易信息

方法名 ：`killReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privateKey | String  | 私钥|
| gasPrice | BigInteger  | gasPrice|
| gasLimit | BigInteger  | gasLimit|

返回值类型：`TransactionReceipt`
返回说明：等待返回交易结果


##  二、DID模块方法调用（DIDService）

### 1.创建did

方法名 ：`create()`
参数说明:无
返回值类型：`DIDAccount`
返回说明：

| 返回值 | 参数类型 | 返回值说明|
| :----| :----  | :----  |
| privateKey | String  | 私钥|
| publicKey | String  |公钥|
| address | String  |亦来云钱包地址|
| did | String  |did地址|
| mnemonic | String  |助记词|

### 2.根据私钥获取DID

方法名 ：`exportByPrivateKey()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| privateKey | String  | 私钥|

返回值类型：`DIDAccount`
返回说明：

| 返回值 | 参数类型 | 返回值说明|
| :----| :----  | :----  |
| privateKey | String  | 私钥|
| publicKey | String  |公钥|
| address | String  |亦来云钱包地址|
| did | String  |did地址|

### 3.根据助记词获取DID

方法名 ：`exportByMnemonic()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| mnemonic | String  | 助记词|

返回值类型：`DIDAccount`
返回说明：

| 返回值 | 参数类型 | 返回值说明|
| :----| :----  | :----  |
| privateKey | String  | 私钥|
| publicKey | String  |公钥|
| address | String  |亦来云钱包地址|
| did | String  |did地址|
| mnemonic | String  |助记词|

### 4.设置DID信息

方法名 ：`setDIDInfo()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| privateKey | String  | 私钥|
| map | Map  | 信息|

返回值类型：`String`
返回说明：

| 返回值 | 参数类型 | 返回值说明|
| :----| :----  | :----  |
| txId | String  | 交易id|

### 5.获取DID信息

方法名 ：`getDIDInfo()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| txidList | List  | 设置同一key返回的txid数组|
| key | String  | 信息key|

返回值类型：`Map`
返回说明：信息Map

##  三、钱包模块方法调用

### 1.ela钱包（ElaWalletService）

####    1.创建钱包

方法名 ：`create()`
参数说明:无
返回值类型：`ElaAccount`
返回说明：

| 返回值 | 参数类型 | 返回值说明|
| :----| :----  | :----  |
| privateKey | String  | 私钥|
| publicKey | String  |公钥|
| address | String  |亦来云钱包地址|
| mnemonic | String  |助记词|

####    2.通过私钥获取钱包

方法名 ：`exportByPrivateKey()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| privateKey | String  | 私钥|

返回值类型：`ElaAccount`
返回说明：

| 返回值 | 参数类型 | 返回值说明|
| :----| :----  | :----  |
| privateKey | String  | 私钥|
| publicKey | String  |公钥|
| address | String  |亦来云钱包地址|

####    3.通过助记词获取钱包

方法名 ：`exportByMnemonic()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| mnemonic | String  | 助记词|

返回值类型：`ElaAccount`
返回说明：

| 返回值 | 参数类型 | 返回值说明|
| :----| :----  | :----  |
| privateKey | String  | 私钥|
| publicKey | String  |公钥|
| address | String  |亦来云钱包地址|

####    4.根据地址获取余额

方法名 ：`balance()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| address | String  | 地址|

返回值类型：`String`
返回说明：余额

####    5.转账

方法名 ：`transfer()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| privatekey | String  | 私钥|
| to | String  | 接收者地址|
| value | String  | 转出金额|

返回值类型：`String`
返回说明：交易hash

####    6.查询交易详情

方法名 ：`transactionInfo()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| txid | String  | 交易txid|

返回值类型：`JSONObject`
返回说明：交易信息

####    7.地址校验

方法名 ：`checkAddr()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| address | String  | 地址|

返回值类型：`Boolean`
返回说明：校验结果

### 2.eth钱包（EthWalletService）

####    1.创建钱包

方法名 ：`create()`
参数说明:无
返回值类型：`EthAccount`
返回说明：

| 返回值 | 参数类型 | 返回值说明|
| :----| :----  | :----  |
| privateKey | String  | 私钥|
| publicKey | String  |公钥|
| address | String  |亦来云钱包地址|
| mnemonic | String  |助记词|

####    2.通过私钥获取钱包

方法名 ：`exportByPrivateKey()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| privateKey | String  | 私钥|

返回值类型：`EthAccount`
返回说明：

| 返回值 | 参数类型 | 返回值说明|
| :----| :----  | :----  |
| privateKey | String  | 私钥|
| publicKey | String  |公钥|
| address | String  |亦来云钱包地址|

####    3.通过助记词获取钱包

方法名 ：`exportByMnemonic()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| mnemonic | String  | 助记词|

返回值类型：`EthAccount`
返回说明：

| 返回值 | 参数类型 | 返回值说明|
| :----| :----  | :----  |
| privateKey | String  | 私钥|
| publicKey | String  |公钥|
| address | String  |亦来云钱包地址|

####    4.根据地址获取余额

方法名 ：`balance()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| address | String  | 地址|

返回值类型：`String`
返回说明：余额

####    5.转账

方法名 ：`transfer()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| privatekey | String  | 私钥|
| to | String  | 接收者地址|
| value | String  | 转出金额|
| gasPrice | BigInteger   | gas价格|
| gasLimit | BigInteger   | gas限制|

返回值类型：`String`
返回说明：交易hash

####    6.查询交易详情

方法名 ：`transactionInfo()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| txid | String  | 交易txid|

返回值类型：`JSONObject`
返回说明：交易信息

####    7.地址校验

方法名 ：`checkAddr()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| address | String  | 地址|

返回值类型：`Boolean`
返回说明：校验结果

####    8.根据地址获取代币余额

方法名 ：`tokenBalance()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| address | String  | 地址|

返回值类型：`String`
返回说明：余额

####    9.代币转账

方法名 ：`tokenTransfer()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 合约地址|
| privatekey | String  | 私钥|
| to | String  | 接收者地址|
| value | String  | 转出金额|
| gasPrice | BigInteger   | gas价格|
| gasLimit | BigInteger   | gas限制|

返回值类型：`String`
返回说明：交易hash

##  四、Exchange模块方法调用

### 1.去中心化托管合约（PlatFormService）

####    1.创建托管合约

方法名 ：`deploy()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| privatekey | String  | 私钥|
| gasPrice | BigInteger   | gas价格|
| gasLimit | BigInteger   | gas限制|
| token721Address | String  | 托管资产合约地址|
| token20Address | String  | 购买资产代币合约地址|

返回值类型：`String`
返回说明：托管合约地址

####    2.资产托管

#####   1.托管资产，直接返回交易hash

######  (1)托管单个资产

方法名 ：`saveApprove()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 托管合约合约地址|
| privatekey | String  | 私钥|
| gasPrice | BigInteger   | gas价格|
| gasLimit | BigInteger   | gas限制|
| _tokenId | String  | tokenid|
| _value | String  | 售卖金额|
| _owner | String  | tokenid拥有者|

返回值类型：`String`
返回说明：交易hash

######  (2)以tokenid数组方式批量托管资产

方法名 ：`saveApproveWithArray()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 托管合约合约地址|
| privatekey | String  | 私钥|
| gasPrice | BigInteger   | gas价格|
| gasLimit | BigInteger   | gas限制|
| _tokenIds | List  | tokenid数组|
| _value | String  | 单价|
| _owner | String  | tokenid拥有者|

返回值类型：`String`
返回说明：交易hash


#####   2.托管资产，返回交易信息

######  (1)托管单个资产

方法名 ：`saveApproveReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 托管合约合约地址|
| privatekey | String  | 私钥|
| gasPrice | BigInteger   | gas价格|
| gasLimit | BigInteger   | gas限制|
| _tokenId | String  | tokenid|
| _value | String  | 售卖金额|
| _owner | String  | tokenid拥有者|

返回值类型：`TransactionReceipt`
返回说明：交易信息

######  (2)以tokenid数组方式批量托管资产

方法名 ：`saveApproveWithArrayReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 托管合约合约地址|
| privatekey | String  | 私钥|
| gasPrice | BigInteger   | gas价格|
| gasLimit | BigInteger   | gas限制|
| _tokenIds | List  | tokenid数组|
| _value | String  | 单价|
| _owner | String  | tokenid拥有者|

返回值类型：`TransactionReceipt`
返回说明：交易信息

####    3.撤销资产托管

#####   1.撤销托管资产，直接返回交易hash

######  (1)撤销单个资产

方法名 ：`revokeApprove()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 托管合约合约地址|
| privatekey | String  | 私钥|
| gasPrice | BigInteger   | gas价格|
| gasLimit | BigInteger   | gas限制|
| _tokenId | String  | tokenid|
| _owner | String  | tokenid拥有者|

返回值类型：`String`
返回说明：交易hash


######  (2)以tokenid数组方式批量撤销托管资产

方法名 ：`revokeApprovesWithArray()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 托管合约合约地址|
| privatekey | String  | 私钥|
| gasPrice | BigInteger   | gas价格|
| gasLimit | BigInteger   | gas限制|
| _tokenIds | List  | tokenid数组|
| _owner | String  | tokenid拥有者|

返回值类型：`String`
返回说明：交易hash


#####   2.撤销托管资产，返回交易信息

######  (1)撤销单个托管资产

方法名 ：`revokeApproveReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 托管合约合约地址|
| privatekey | String  | 私钥|
| gasPrice | BigInteger   | gas价格|
| gasLimit | BigInteger   | gas限制|
| _tokenId | String  | tokenid|
| _owner | String  | tokenid拥有者|

返回值类型：`TransactionReceipt`
返回说明：交易信息


######  (2)以tokenid数组方式批量撤销托管资产

方法名 ：`revokeApprovesWithArrayReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 托管合约合约地址|
| privatekey | String  | 私钥|
| gasPrice | BigInteger   | gas价格|
| gasLimit | BigInteger   | gas限制|
| _tokenIds | List  | tokenid数组|
| _owner | String  | tokenid拥有者|

返回值类型：`TransactionReceipt`
返回说明：交易信息



####    4.购买资产

#####   1.购买资产，直接返回交易hash

######  (1)购买单个资产

方法名 ：`transfer()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 托管合约合约地址|
| privatekey | String  | 私钥|
| gasPrice | BigInteger   | gas价格|
| gasLimit | BigInteger   | gas限制|
| _tokenId | String  | tokenid|
| _value | String  | 售价|
| _owner | String  | tokenid拥有者|

返回值类型：`String`
返回说明：交易hash


######  (2)以tokenid数组方式批量撤销托管资产

方法名 ：`transferWithArray()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 托管合约合约地址|
| privatekey | String  | 私钥|
| gasPrice | BigInteger   | gas价格|
| gasLimit | BigInteger   | gas限制|
| _tokenIds | List  | tokenid数组|
| _value | String  | 总售价|
| _owner | String  | tokenid拥有者|

返回值类型：`String`
返回说明：交易hash


#####   2.购买托管资产，返回交易信息

######  (1)购买单个资产

方法名 ：`transferReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 托管合约合约地址|
| privatekey | String  | 私钥|
| gasPrice | BigInteger   | gas价格|
| gasLimit | BigInteger   | gas限制|
| _tokenId | String  | tokenid|
| _value | String  | 售价|
| _owner | String  | tokenid拥有者|

返回值类型：`TransactionReceipt`
返回说明：交易信息


######  (2)以tokenid数组方式批量撤销托管资产

方法名 ：`transferWithArrayReceipt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 托管合约合约地址|
| privatekey | String  | 私钥|
| gasPrice | BigInteger   | gas价格|
| gasLimit | BigInteger   | gas限制|
| _tokenIds | List  | tokenid数组|
| _value | String  | 总售价|
| _owner | String  | tokenid拥有者|

返回值类型：`TransactionReceipt`
返回说明：交易信息

####    5.获取托管资产数

方法名 ：`getAssetCnt()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 托管合约合约地址|
| _owner | String  | 托管者地址|

返回值类型：`BigInteger`
返回说明：托管资产数

####    6.获取上架资产信息

方法名 ：`getApproveinfo()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| contractAddress | String  | 托管合约合约地址|
| tokenid | String  | tokenid|

返回值类型：`PlatFormApproveInfo`
返回说明：

| 返回值参数 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| owner | String  | token拥有者|
| tokenid | String  | tokenid|
| value | String  | 单价|

##  五、Utility

### 1.获取助记词

方法名 ：`getMnemonic()`
参数说明:
返回值类型：`String`
返回说明：助记词

### 2.获取KeyStore

方法名 ：`getKeyStore()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| privateKey | String  | 私钥|
| pwd | String  | 密码|

返回值类型：`String`
返回说明：keyStone

### 3.解析keyStore

方法名 ：`getPrivateKeyByKeystore()`
参数说明:

| 参数名 | 参数类型 | 参数说明|
| :----| :----  | :----  |
| Keystore | String  | Keystore|
| pwd | String  | 密码|

返回值类型：`String`
返回说明：私钥
