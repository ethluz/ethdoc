################################################################################
常见问题
################################################################################

.. contents::
  :local:
  :depth: 2

问题
==============================================================================================

什么是以太坊？
----------------------------------------------------------------------------------------------
以太坊是一个由被成为以太币的加密货币所支持的去中心化的智能合约平台。“ :ref:`what-is-ethereum` ”这一节提供了关于它的工作方式的更详尽的介绍。

我听说过以太坊，但什么是Geth、Mist、Ethminer和Mix呢？
----------------------------------------------------------------------------------------------
* **Geth** ：这是个以太坊节点的Go语言实现，是与以太坊区块链交互的基础。在本地运行这个程序可以使你很容易地和以太坊区块链进行交互。请参考 `go-ethereum installation instructions <https://github.com/ethereum/go-ethereum/wiki/Building-Ethereum>`_ 。
* **Mist** ：这相当于以太坊平台中的Web浏览器，它作为一个GUI来显示与你交互的账户及合约。它也允许你在图形界面中创建并与合约进行交互而不使用命令行。如果你不是一个开发者，仅仅想存储以太币并与以太坊合约进行交互，Mist就是该使用的程序。你可以在 `Mist发布页面 <https://github.com/ethereum/mist/releases>`_ 下载它。
* **Ethminer** ：一个独立的矿工。它可以用来挖矿或为挖矿做评估。它与eth、geth和pyetherem兼容。请查看 :ref:`mining` 获得更多信息。
* **Mix** ：这是为DApp作者们提供的集成开发环境，使用它可以在以太坊平台上快速构建原型和调试去中心化应用程序。更多信息请参考 `Mix GitHub Page <https://github.com/ethereum/mix>`_ 。

我如何在区块链上存储大型文件？
----------------------------------------------------------------------------------------------
通常来讲，因为在以太坊区块链上的存储成本很高，所以一般不会在其上存储大型文件或者数据块。你可以使用一个第三方的解决方案，比如Swarm或者IPFS。Swarm是一个为以太坊设计的分布式文件存储方案。IPFS是一个非以太坊工程，但与以太坊有紧密的关联；它可以独立使用并且可能会在未来被添加到Swarm之下作为独立的层级。参考 `this Ethereum StackExchange post on the topic <http://ethereum.stackexchange.com/questions/1000/what-are-some-proposed-ways-of-storing-data-in-ethereum/1001#1001>`_ 获得更多信息。

以太坊是基于比特币的么？
----------------------------------------------------------------------------------------------
仅仅在使用了比特币开创的区块链技术这方面，是的。以太坊是一个独立的区块链，并且使用了很多不同于比特币区块链的重要技术。更详尽的解释请参考 `this Ethereum StackExchange answer <http://ethereum.stackexchange.com/questions/700/what-are-the-differences-between-bitcoin-blockchain-and-ethereum-blockchain>`_ 。

以太坊的未来是什么？
----------------------------------------------------------------------------------------------
以太坊开发者正在计划一个在未来由工作量证明共识到权益证明共识的切换。他们也在研究如何在区块链上保存隐私数据的扩展方案。

账户和“钱包合约”的区别是什么？
----------------------------------------------------------------------------------------------
一个账户是你的公/私钥对来在区块链上作为你的标示，请参考术语表中的“账户”。而“钱包合约”是一种以太坊智能合约，它可以保护你的以太币和身份，并提供一些诸如多重签名认证、程序化的储蓄/取出限制等特性。一个钱包合约可以简单的由以太坊钱包的Mist图形客户端创建。

秘钥文件是否仅能在我下载客户端的电脑上访问？
----------------------------------------------------------------------------------------------
不是。你可以随意导出或移动你的秘钥文件，但记得做好备份，记住你在哪些电脑上存储了它们。

下载区块链大概要花多长时间？
----------------------------------------------------------------------------------------------
以太坊区块链在不断的增长，到2016年3月已经达到大约10GB。下载全部数据的时间，取决于你能链接到多少节点、你的互联网链接速度及一些其他条件。请参考 :ref:`download-the-blockchain-faster` 来获知更快地同步区块链的方法。

我如何获得进出一个地址的所有交易列表？
----------------------------------------------------------------------------------------------
你需要手工把交易信息从区块链中导出。或者你可以使用第三方的浏览器API，比如 `Etherchain <https://etherchain.org/apidoc>`_ 。然而对于合约执行的交易，你可以通过过滤合约日志来实现。

一个合约可以自己支付它的执行消耗么？
----------------------------------------------------------------------------------------------
不，这不可能。执行操作所需的气，必须有提交执行请求的地址所提供。

一个合约可以调用其他合约么？
----------------------------------------------------------------------------------------------
是的，可以。请参考 `合约间的交互 <https://dappsforbeginners.wordpress.com/tutorials/interactions-between-contracts/>`_ 。

一个交易可以进行离线签名，然后提交到在线装置上么？
----------------------------------------------------------------------------------------------
可以，你可以从 `Icebox <https://github.com/ConsenSys/icebox>`_ 参考具体方案。

如何获得测试网络的以太币？
----------------------------------------------------------------------------------------------
请参考 :ref:`test-networks` 。

一个交易是否可以由第三方发送？比如，将交易广播外包
----------------------------------------------------------------------------------------------
技术上说，可以。但比特币签名时的一个重要限制妨碍了这么做：在以太坊中，每个交易都有一个nonce（更确切地说，每个账户都会有个计数器，记录它已经发送了多少交易。如果当前账户发送过3个交易，这个账户的nonce将是3）。

以太坊合约可以通过第三方API来拉取数据么？
----------------------------------------------------------------------------------------------
不行，以太坊合约不能从外部数据源拉取数据。然而，通过交易从外部站点推送数据（例如天气网站或股票价格）到以太坊合约是可能的。有一些“权威”的有偿服务可以提供到以太坊拉取/推送数据的兼容性。

以太坊网络上发送的数据和合约内容是加密的么？
----------------------------------------------------------------------------------------------
以太坊网络中的数据和合约是经过编码的，但不是加密的。所有人都可以审计合约的行为和发送给他们的数据。然而，你可以随时在本地加密数据之后再把它们广播到网络上。

我可以在以太坊网络上存储隐私数据或者密码么？
----------------------------------------------------------------------------------------------
以太坊上的所有数据都是公开的。在以太坊合约中存储隐私数据或密码是无法保证它们不被其他人看到的。通过代码模糊（code obfuscation）和其他技术手段使这成为可能的研究工作正在进行。Vitalik Buterin写的 `Privacy on the Blockchain <https://blog.ethereum.org/2016/01/15/privacy-on-the-blockchain/>`_ 是一个很好的参考。

以太坊如何对付那些中心化的矿池？
----------------------------------------------------------------------------------------------
基于以太坊工作量证明的共识算法有两种主要方法对付中心化的挖矿（ `原文 <http://ethereum.stackexchange.com/questions/549/how-does-ethereum-avoid-mining-pool-centralization>`_ ）。

* 首先是降低因孤儿区块（orphaned blocks，即因主分叉增长而缺失父区块导致被废弃的区块，译者注）导致的损失，以使独立的矿工有更多的参与度。

  * 以太坊挖矿算法的这部分，即GHOST，使包含最近的孤儿区块的区块产出节点和包含了这些孤儿区块的节点都能获得一些降低的报酬（与主分叉中的区块产出节点获得的报酬相比，译者注）。这些被包含的从“祖父”看是孤儿或更早的区块通常是指那些“叔舅”区块（即因为分布式计算/共识校验的原因，导致这些区块的父区块的父区块相同，但父区块不同，译者注），因为关于中立性别的术语“ommer”并不广为人知。

* 第二个用以对抗中心化挖矿方法是以太坊的工作量证明共识算法是有ASIC抗性的。

  * 通过阻止那些用专门设计生产的计算硬件来争取统治地位的挖矿，独立的矿工可以保持竞争力甚至有了某种在它们那个硬件投资等级上的利润优势，因为它们可以使用那些商品化的硬件（比如普通消费者所使用的显卡）。

以太坊如何处理一直在增长的区块链规模？
----------------------------------------------------------------------------------------------
围绕区块链的扩展有很多讨论。这个问题在 `Ethereum StackExchange post <http://ethereum.stackexchange.com/questions/521/what-does-it-mean-to-run-code-on-the-blockchain-wouldnt-blockchain-become-hu>`_ 和 `Vitalik Buterin的这篇博客 <https://blog.ethereum.org/2014/02/18/ethereum-scalability-and-decentralization-updates/>`_ 上可以得到部分的解答。

以太坊如何确保提供每秒10000+的交易能力？
----------------------------------------------------------------------------------------------
以太坊计划在开发路线图的Serenity阶段（下一个生产版本，译者注）实现一个权益证明共识协议。关于以太坊的权益证明的更多信息以及它如何提高秒级交易量可以 `在这里找到 <https://blog.ethereum.org/2015/08/01/introducing-casper-friendly-ghost/>`_ 。

智能合约保存在哪儿？
----------------------------------------------------------------------------------------------
待续。

你的问题依然没有得到解答？
----------------------------------------------------------------------------------------------
请在 `Ethereum StackExchange <http://ethereum.stackexchange.com/>`_ 向社区提问。
