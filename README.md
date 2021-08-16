# hegic2dfinity

## whitepaper
https://ipfs.io/ipfs/QmWy8x6vEunH4gD2gWT4Bt4bBwWX2KAEUov46tCLvMRcME
- 将期权writer的无限风险转移到LP提供者上
- LP的资金可以用在多个hedge contract上，增加了资金的利用率，长期来看，回报优于solo options writer
- buy a Put hedge contract的步骤
  - 设置价格
  - 设置到期时间
  - 链接chainlink获取ETH实时价格
  - 以at-the-money hedge contract为例，它的premium包括了4%rate和1%的settlement fee???
  - 创建hedge contract时，会创建一个end timestamp（调用release func）

- 质押稳定币的步骤（与uniswap上基本一致）
  - hedge contracts writer的理论的年化收益在27%到108%之间
  - 卖方质押稳定币（DAI， USDC， USDT）
  - 将稳定币如DAI加入流动性池后，得到writeDAI（erc20），这个token决定了买方premium的分配
  - 通过burn writeDAI可以赎回DAI

- sell a Put hedge contract的步骤
  - 假如买方买了一张hedge contract，费用是10usdt，以eth支付，hegic会在uniswap中将eth转化为DAI，最终writer的收益以DAI计算
  - hegic的配置来看，最多80%的DAI会被锁定，有20%的DAI始终用来赎回
  - 当池子中的DAI不足时（因为锁定），用户可以发送请求在合约到期时立马赎回DAI，但是这个过程需要排队

- 定价模型与一些QA
  - 与传统的BS模型相对应，这里使用固定的rate，简化计算
  - 开一张hedge contract在不行权的情况下也要缴纳settlement fee？？？？？
  - 在Hegic上，holder可以在任何时候settle，甚至不需要达到break-even price，
  - 在持有hedge contract的情况下，开发者可以开发新的去中心化的二级市场交易平台来交易持仓
  - Hegic的最注重的并不是提供更便宜的contract（虽然它基本上做到了），主要是去中心化平台带来的trustless, non-custodial type
  - 在Hegic中质押DAI时，不仅会收到作为writer的premium，同时还有DAI saving rate

## dfinity开发难点
- icp钱包
- 到期时难以触发事件(可能不需要？直接是用户直接触法)
- 链上的uniswap兑换
  
