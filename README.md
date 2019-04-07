# 牛排豪丝 简易PoS指南
几句话总结各种 Proof of Stake 区块链 Staking 抵押/权益 技术

# 目录
1. [链](https://github.com/mingrui/stake-house/blob/master/README.md#%E9%93%BE)
2. [托管](https://github.com/mingrui/stake-house/blob/master/README.md#%E6%89%98%E7%AE%A1)
3. [机构](https://github.com/mingrui/stake-house/blob/master/README.md#%E6%9C%BA%E6%9E%84)
4. [安全](https://github.com/mingrui/stake-house/blob/master/README.md#%E5%AE%89%E5%85%A8)
5. [Defi](https://github.com/mingrui/stake-house/blob/master/README.md#defi)

# 链

## Cosmos
__Vision: 底层币Atom并不想成为现金货币，而是纯粹的抵押通证。是更纯粹的以太坊，最终的价值为共识治理的权利通证。在Atom作为底层治理通证的保护下，上层应用可以自主选择应用内的现金货币，比如Bitcoin或者稳定币等等。__

|共识系统|Tendermint Bonded PoS|
|---|---|
|抵押币|Atom|
|出块节点|100个初始节点，10年增长到300个|
|委托功能|底层协议原生支持，普通持币用户必须通过验证节点委托质押|
|锁定数量|委托没有最低值，节点需要竞选|
|锁定时间|瞬间锁定，21天解锁|
|硬件要求|验证节点需要专业运维支持|
|惩罚机制|Hard Slashing(硬削减) 原因：1.双签名 2.下线时间过长 后果：永远丢失抵押的Atom|
|抵押回报|报块奖励，手续费；7-20% 通胀率，经济模型激励抵押|
|抵押投票|链上治理投票权益，1个Atom为1票|
|出块节点竞选||
|推荐池|[星火](https://cosmos.sparkpool.com/) [Wetez](https://www.wetez.io/mhomepagecn)|

* 抵押风险
  * 验证节点作恶风险：delegator资金会受到Slashing，永远丢失抵押的Atom。选择验证节点格外重要
  * 通胀浮动风险：Atom 通胀率设计鼓励抵押：如果抵押率过低，通胀率会持续增长，直到达到目标抵押率，目前66%
  * DDS
  * 私钥风险
  
官方文档：https://cosmos.network/docs/gaia/validators/validator-faq.html#general-concepts  
参考：
* [Cosmos 背后的关键理念](https://blog.chorus.one/the-key-ideas-behind-the-cosmos-network/)
* [Chorus.one 权益池简介](https://blog.chorus.one/proof-of-stake-contenders-cosmos-network/)
* [Coinmonks Staking 教程](https://medium.com/coinmonks/cosmos-atom-staking-guide-4a4e703c998a)
* [验证节点可视化：可在右侧菜单看到所有验证节点](https://nylira.net/3d)
* [Validator 运转费用和盈利模式](https://medium.com/@davekaj/how-to-become-a-cosmos-validator-276862d5bfc7)

## Irisnet
__Vision: 和Cosmos用的相同的共识协议__

由于共识协议由Tendermint团队合作提供，Staking 机制与 Cosmos 基本相同，特别的一点是有一个官方钱包 Rainbow Wallet，这个钱包里面直接支持托管服务。比如Irisnet投资方 NGC 在官方的[公众号内推荐用 Rainbow 钱包进行托管](https://mp.weixin.qq.com/s?__biz=MzU4NTY0MDE1Mg==&mid=2247483872&idx=1&sn=43d90ca0c62144c39202ecaf86bd80a8&chksm=fd863057caf1b941ca6c3b8d1f3a9829fcb8fe3365a242d02ad4614fc1e3e02d351edce485fa&scene=0&xtrack=1)。Rainbow钱包用户内，如果用户持有Cosmos的ATOM，会获得总量5%的 IRISnet Airdrop

参考:  
* [Hitchhikers Guide to Irisnet](https://medium.com/cryptium-irisnet/the-hitchhikers-guide-to-the-irisnet-56bed7439c4b)

## Tezos
__Vision: XTZ想成为现金货币，竞争对手是Bitcoin，底层协议更容易更改，所以对上层的生态开发并不是主要考虑。__

特殊词汇：  
* Bakers：出块节点，直接获取奖励
* Baking：通过 Staking 抵押 出块
* Endorser：通过为Baker背书获取奖励
* Accuser：监控Baker，Endorser作恶获取奖励

|共识系统|Liquid PoS|
|---|---|
|抵押币|XTZ|
|Baker节点|节点数量浮动，理论上最高值为80,000个|
|委托功能|底层协议原生支持，普通用户不需要通过委托质押，可以自己成为Baker出块|
|锁定数量|自己Bake需要开始最少10,000 XTZ，慢慢降低到2,000 XTZ。委托没有下限|
|锁定时间|瞬间锁定，"several weeks" 几周解锁|
|硬件要求|普通电脑，稳定网络|
|惩罚机制|Accuser 主动检查作恶：1.Double Baker 2.Double Endorser。作恶节点的一半抵押币支奖励给Accuser|
|抵押回报|每年最多5.51%通胀，回报由Baker选择如何分配给自己的委托人，Endorser和Accuser也会产生回报|
|抵押投票|不是1 XTZ 1票，而是由Baker产出的一份额的币（10,000 XTZ）统一称作一个Roll（面包条），一个Roll一票|
|Baker竞选|Baker不需要特殊竞选任何人可以在抵押币量足够的情况下，随时成为Baker|
|推荐池|[Wetez](https://www.wetez.io/mhomepagecn)|

* 抵押风险
  * 验证节点不付出Baking回报，但是用户可以很容易发现并且很快速的切换委托，只会损失本轮委托
  * 与 Cosmos 不同，验证节点作恶，用户的抵押币不会受到损失
  * DDoS
  * 私钥风险

官方文档：http://tezos.gitlab.io/mainnet/introduction/howtorun.html#delegating-your-coins  
参考：
* [Cryptium Labs Tezos 简介](https://medium.com/cryptium/the-hitchhikers-guide-to-tezos-36f112662074)
* [Liquid PoS](https://medium.com/tezos/liquid-proof-of-stake-aec2f7ef1da7)
* [从Baker的经验](https://medium.com/tezos/its-a-baker-s-life-for-me-c214971201e1)
* [All Bakers](https://www.mytezosbaker.com/)

# 托管

# 机构

## Irisnet
网站上列出的机构:  
[AMINO Capital](https://www.aminocapital.com/)  
[Bibox](https://www.bibox.com/)  
[Huobi Capital](https://www.hbg.com/en-us/capital/)  
[GBIC](https://gbic.io/)  
[8Decimal Capital](http://8dcapital.com/)  
[币乎](https://bihu.com/)  
[BA Capital](https://medium.com/carryprotocol/bitmains-angel-investor-bitfinex-shareholder-join-carry-as-strategic-investor-b50ba06f7f39) 不确定  
[BKFUND](http://bkfund.io/)  
[拜占庭资本](http://www.markchain.com/)  
[CHAINPE](http://www.chainpe.com/en/)  
[CP](https://chainpool.io/)  
[Coeffecient Ventures](http://coefficient.network/)  
[共识资本](http://consensuscapital.ca/)  
读数基金 DUSHU Foundation  
[Genblock Capital](https://genblock.capital/)  
[Hayek Capital](http://hayek.capital/index_en.html)  
[INK Labs](https://ink.one/)  
[LINKVC](http://www.linkvc.com/)  
[MediShares](http://medishares.org/#/)  
[界后](http://www.milestonevc.com/index.html)  
[Nirvana Capital](http://nirvana.capital/)  
[Neo Global Capital](https://www.ngc.fund/)  
[Origin Capital](https://www.theorigincapital.com/)  
[Satoshi Fund](https://satoshi.fund/)  
[硅谷密探](http://www.svinsight.com/)  
[时戳资本](https://www.crunchbase.com/organization/timestamp-capital#section-overview)  
[回向基金](https://www.block123.com/zh-hans/nav/522980786639.htm)  
[U Network](https://u.network/)  
[九合创投](http://www.unityvc.com/zh.html?12h10c)  
[Univalues Associates](https://uva.fund/)  
[水滴资本](http://waterdrip.io/)  
[一道资本](http://www.xiniudata.com/investor/f8e5958235b4484ebaec0acca4586f4c/overview)


# 安全


# Defi
Decentralized Finance  
这个部分比较有趣，本质上可以把Defi的 Staking 理解为两个部分，第一个部分因为 Staking 代表了投票权益，所以做 Staking 的一个好处是可以对 Dapp 的治理作出影响。第二个部分是 Staking 同时需要带来收益，目前能看到几种 Defi Dapp 把自己包装成了一个建立在 ETH 经济基础上的金融衍生品。简单的逻辑是把我的币借给一个中心机构，这个机构按时给我返利。这种返利可能是简单直接的利息，也可能是一种相当于短期 Margin 贷款的权利。

那么为什么 Defi 的 Staking 非常值得关注，因为在某种意义上讲，这才是回到了 ETH 真正实用的本源。比如一个普通用户，为什么要在 2017 年的时候买入 ETH？ 我想压倒性的原因就是因为入金 ICO，ICO 就是 Defi。

如果你的记忆够久远，可能会想到比 ETH 更早之前，Bitcoin 生态的融资模式，当时的融资币被叫做 Altcoin，ETH 在最开始也是一个 Altcoin。从那个时候，到现在我觉得最有意思的是 Doge，真的是信仰币。和之前最大的不同，要归功于 [ERC-20](https://eips.ethereum.org/EIPS/eip-20)，就是因为这个功能，把发币门槛有一次降低，整个发币流水线变得无比顺滑。可能我这么说，会引起做技术朋友们的不满，但是就国内来讲，其实我们这几年的用户就是炒币的人。我总会抱着研究用户的好奇心请，加很多炒币群，维权群，喊单群，看到这些真实用户的日常行为，还是非常能反映现在区块链行业还真的太原始了。

ERC-20 过后的一个大功能是能做“链上唯一艺术品收藏”的 [ERC-721](http://erc721.org/) Token，逻辑很简单，就是炒。但是目前来看大热过一段时间后就没有什么流量了，在以后可能会慢慢找到出路。但是我觉得，一个唯一性收藏品的收藏品，放到链上，由于本质上不是货币，所以转手的次数不会很多，可能炒币的耐久性不是特别能持续。但是如果以后发展成可以把一个唯一性的收藏品变成股份制，比如一只绿色海盗猫分成1000份，之后用户可以交易绿色海盗猫猫股份，这个股份的转手次数就会高很多了，带来的可玩性也更大，更多人可以参与到最珍贵的收藏品的交易中去。

原始的链上融资，简单的通过 Bitcoin 融资，之后开发团队再发币，给比特币带来的买入压力远远小于 ERC-20 为 ETH 带来的买入压力。ERC-20 带来的买入压力远远大于 ERC-721 带来的买入压力。那么下一个带来超大买入压力的会是什么呢？一个大的聚焦点应该放在 Ethereum 的新 Token 功能上，现在 ETH 的开发生态是最完善的，在上面的发币的最大好处是流通，有了流通性就有了人和人之间的去中心化交易，有了去中心化交易就有了真正的可玩性。

转回来看 Defi ，用 MakerDAO 来做例子，能看到增长是爆发性的，看图的时候能看到曲线都是竖起来往上走。记得 DevCon3 的时候，它还是最后一天在旁边小屋子讲的一个小项目（DevCon3 最受欢迎的项目是用小额支付去遥控一个赛车，然而回头看可能微信群里的炒币用户并不需要小额支付）。按照前两段瞎忽悠的分析，为什么 Maker 好玩，因为它带来了很大的流动性和可玩性。把币抵押过去之后并不是事就完了，玩家还需要去一直调控自己的策略，这种可玩性这么强的系统会吸引一小波爱动脑筋的玩家参与，这些玩家会鼓动亲朋好友一起来玩，因为你自己想想，这个系统设计的的确好玩。作为经济学位的我来说，你说我这辈子有几次机会能参与到制定货币政策的过程中去？MakerDAO就可以，来来来，当个央行行政人员来投个票来玩玩。基本逻辑简单透明，全社区可以参与其中，抵押出 Dai 来之后，立马变成看涨的加杠杆工具，期间还充满了和 1 USD 不能完美对标带来的波动行和投机行为，简直是，非常好玩。

## MakerDAO  
__Vision: DAI为稳定货币，MKR为治理通证__

[Stats](https://www.daiprice.info/)  

目前的最大Use Case：ETH长期持有者需要短期现金流动性但是又不想卖掉自己手中的ETH，例如Aragon项目方的[抵押贷款](https://diar.co/ethereum-ico-treasury-balances/)，这种做法相当于加杠杆看长ETH。如果ETH跌太多，会被 margin call.

MakerDAO 没有 直接的 Staking 概念，但是MKR通证有设计好的持币升值逻辑：MKR通证作为系统的治理通证，有投票权，那么MKR的持币人并不需要特殊的Staking Contract去做抵押。整个抵押过程可以想象为全自动的过程，因为整个系统的借贷利率是0.5%，这个利息的收取方法可以简单理解直接烧掉等价值的在外流通的MKR通证，所以长期持MKR人理论上直接享受升值的快感。

这么来讲的话，就能理解为什么coinbase的[新闻](https://blog.coinbase.com/coinbase-custody-launches-staking-support-for-tezos-makerdao-governance-to-follow-68f7bc51bc53)标题是Tezos Staking & MakerDAO Governance，而不是MakerDao 'Staking'。

参考：
* [Awesome MakerDAO](https://github.com/makerdao/awesome-makerdao/blob/master/README.md)
* [Vision Hill MakerDAO 案例学习](https://medium.com/vision-hill-blog/a-makerdao-case-study-47a31d858be5?fbclid=IwAR254XvvWb79O945Luk9ImJfpz8E1qQ0wfyc1LjjZfh3-_a9nPq9y7Dn9OQ)
