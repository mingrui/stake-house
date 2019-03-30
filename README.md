# 牛排豪丝 简易PoS指南
几句话总结各种 Proof of Stake 区块链 Staking 抵押 技术

# stake-house
fast food style stacking summary for Proof of Stake blockchains

# Cosmos
官方文档：https://cosmos.network/docs/spec/staking/  
参考：https://blog.chorus.one/proof-of-stake-contenders-cosmos-network/

|共识系统|Tendermint Bonded PoS|
|---|---|
|抵押币|Atom|
|验证节点|100个初始节点，10年增长到300个|
|委托功能|底层协议原生支持|
|锁定时间|瞬间锁定，21天解锁|
|惩罚机制|Hard Slashing(硬削减) 原因：双签名，下线时间过长 后果：永远丢失抵押的Atom|
|抵押回报|报块奖励，手续费；7-20% 通胀率|
|抵押投票|链上治理投票权益，1个Atom为1票|
|权益池|[星火](https://cosmos.sparkpool.com/) /// [Staked.us](https://staked.us/stake/opportunities/)|

* Delegation risk: 验证节点作恶，delegator资金会受到Slashing，永远丢失抵押的Atom。选择验证节点格外重要
* Atom 通胀率设计鼓励抵押：如果抵押率过低，通胀率会持续增长，直到达到目标抵押率，目前66%
