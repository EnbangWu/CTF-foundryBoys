事实上，如今，为DeFi运营付费是不可能的。

一群朋友发现了如何通过在一个交易中批量处理来稍微降低执行多个交易的成本，因此他们开发了一个智能合约来执行此操作。

他们需要这个合约是可升级的，以防代码包含错误，他们还想阻止团队外的人使用它。为此，他们投票并分配了两个在系统中具有特殊角色的人：
管理员：有权更新智能合约的逻辑；
所有者：控制允许使用合约的地址白名单。
合同已部署，该组被列入白名单。每个人都为他们对抗邪恶矿工的成就而欢呼。

他们几乎不知道，他们的午餐钱处于危险之中……
你需要劫持这个钱包，去成为代理的管理员。

&nbsp;
可能有帮助的注意点:
* 了解委托调用的工作原理以及执行调用时 msg.sender 和 msg.value 的行为方式。
* 了解代理模式及其处理存储变量的方式。
