# web3 主要是去中心化的区块链
## 开发语言和框架
### solidity （智能合约首选语言）
- 特殊的开发技巧，防止漏洞问题
- https://www.jianshu.com/p/7d207bdb8b9c
### https://remix.ethereum.org/#optimize=false&runs=200&evmVersion=null&version=soljson-v0.8.7+commit.e28d00a7.js sol开发ide
### Truffle sol的开发框架
-  truffle-config.js 可以修改默认的链接节点信息。默认是本地的链接
- 可以使用本地的节点来进行测试，使用ganache 来实现一个本地的，
### web3js 主要是和以太坊节点通信，获取合约等信息
### metamask是浏览器钱包，方便测试，mist等
- 使用助记词和密码来实现登陆
### rust（潜在的语言，不仅仅是智能合约）
### OpenZeppelin 实现对代码健壮性的验证
### Hardhat 调试以太坊的测试环境
### ethers.js 以太坊区块链及其生态系统提供一个小而完整的 JavaScript API 
### WebAssembley 
- web本地化代码，提升性能
# EOS 和以太坊
- 两个去中心的应用平台，EOS是没有gas消耗，以太坊需要gas消耗
- 以太坊目前也是pos生成代币
#相关概念
## 共识
### pow 工作量证明，hash值计算比特币
### pos权益证明、dpos委托权益证明 ，不需要消耗资源，只需要购买代币
### PoH 历史证明
## 链
- 公共链 所有人都可以访问
- 联盟链 一定的组织人员可以访问
- 私有链 需要授权用户访问
## 分叉
- 硬分叉 增加新的特性，对旧分支不认可的就是硬分叉
- 软分叉 同时生成的两个链，矿工会随机一个，但是在发现有最长的链后都统一从最长链上继续工作，所以最终会丢弃短链，这个就是软分叉
## dao 
- 分布式自治组织 去中心化组织，在这个组织上默认执行组织规则
## 默克尔树
- 每个节点存储一个区块的hash值，防止被篡改
## 侧链
- Layer 2 链下扩展性能，但是保留区块链的去中心化能力
## 以太的代币单位
- wei
- 
- 以太=10^18wei
