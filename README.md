# 牛排豪丝 简易PoS指南
几句话总结各种 Proof of Stake 区块链 Staking 抵押/权益 技术

# Cosmos
官方文档：https://cosmos.network/docs/spec/staking/  

参考：
* [Chorus.one 权益池简介](https://blog.chorus.one/proof-of-stake-contenders-cosmos-network/)
* [Coinmonks Staking 教程](https://medium.com/coinmonks/cosmos-atom-staking-guide-4a4e703c998a)
* [验证节点可视化：可在右侧菜单看到所有验证节点](https://nylira.net/3d)

|共识系统|Tendermint Bonded PoS|
|---|---|
|抵押币|Atom|
|验证节点|100个初始节点，10年增长到300个|
|委托功能|底层协议原生支持，普通持币用户必须通过验证节点委托质押|
|锁定数量|委托没有最低值，节点需要竞选|
|锁定时间|瞬间锁定，21天解锁|
|硬件要求|验证节点需要专业运维支持|
|惩罚机制|Hard Slashing(硬削减) 原因：双签名，下线时间过长 后果：永远丢失抵押的Atom|
|抵押回报|报块奖励，手续费；7-20% 通胀率，经济模型激励抵押|
|抵押投票|链上治理投票权益，1个Atom为1票|
|节点竞选||
|推荐池|[星火](https://cosmos.sparkpool.com/)|

* 抵押风险
  * 验证节点作恶风险：delegator资金会受到Slashing，永远丢失抵押的Atom。选择验证节点格外重要
  * 通胀浮动风险：Atom 通胀率设计鼓励抵押：如果抵押率过低，通胀率会持续增长，直到达到目标抵押率，目前66%

# Tezos
官方文档：http://tezos.gitlab.io/mainnet/introduction/howtorun.html#delegating-your-coins

参考：
* [Cryptium Labs Tezos 简介](https://medium.com/cryptium/the-hitchhikers-guide-to-tezos-36f112662074)
* [Liquid PoS](https://medium.com/tezos/liquid-proof-of-stake-aec2f7ef1da7)
* [Bakers](https://www.mytezosbaker.com/)

特殊词汇：  
* Bakers：验证节点  
* Baking：Staking 抵押

|共识系统|Liquid PoS|
|---|---|
|抵押币|XTZ|
|验证节点|节点数量浮动，理论上最高值为80,000个|
|委托功能|底层协议原生支持，普通用户不需要通过委托质押|
|锁定数量|自己Bake需要开始最少10,000 XTZ，慢慢降低到2,000 XTZ。委托没有下限|
|锁定时间|瞬间锁定，"several weeks" 几周解锁|
|硬件要求|普通电脑，稳定网络|
|惩罚机制||
|抵押回报||
|抵押投票||
|节点竞选||
|推荐池||

* 抵押风险
 * 验证节点不付出手汇报，但是用户可以很容易发现并且很快速的切换委托
 * 与 Cosmos 不同，验证节点作恶，用户的抵押币不会受到损失
