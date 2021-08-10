# hegic2dfinity

## whitepaper
https://ipfs.io/ipfs/QmWy8x6vEunH4gD2gWT4Bt4bBwWX2KAEUov46tCLvMRcME
- 将期权writer的无限风险转移到LP提供者上
- LP的资金可以用在多个hedge contract上，增加了资金的利用率，长期来看，回报优于solo options writer
- buy a Put hedge contract of ETH的步骤
  - 设置价格
  - 设置到期时间
  - 链接chainlink获取ETH实时价格
  - 以at-the-money hedge contract为例，它的premium包括了4%rate和1%的settlement fee???
  - 创建hedge contract时，会创建一个end timestamp（调用release func）

- sell a Put hedge contract of ETH的步骤
  - hedge contracts writer的理论的
  
