:github_url: https://github.com/laalaguer/ethereum-compass/blob/master/ch2/app.rst

资料篇：常用钱包 App
====================================

**有没有钱包 App 代我管理私钥？**

在实际生产环境中，有多种钱包应用替我们管理了私钥，并替我们生成 keystore, 便于我们在不同钱包应用之间转移自己的账户信息。

这些软件多数还支持 **“助记词”** [#]_ 方式生成私钥，让用户摆脱记住一串16进制字符串的困境。

常见的客户端满足如下功能与特点：

   - 代替用户管理单一或多把私钥。
   - 与区块链网络同步，追踪用户的账户余额。
   - 正确设置区块链交易费，设置交易体的内容。
   - 高级的客户端具备智能合约调试与互动功能。
   - 代码开源，受到公众信任。

下面，我们挑选一些桌面端以及手机端的常见钱包应用程序向读者介绍。

.. topic:: Geth

   运行环境：Windows/Linux/Mac

   这是用 Golang 语言写作的，由 **官方发布** [#]_的命令行客户端 。它能够在计算机上运行并提供强大的账户管理、区块链同步、区块浏览、交易组织以及智能合约调试功能。是主要面向开发者的钱包，开发进度紧跟以太坊黄皮书的定义规范与最新的社区提议。用户能够选择同步主网或者是测试网络，也能够脱离上述网络构建自己的私有以太坊链。


.. figure:: /img/Picture10.png
   :align: center
   :width: 600 px

   Geth客户端，正在同步区块链数据


.. topic:: Parity

   运行环境：Windows/Linux/Mac

   Parity 客户端号称是世界上最快最轻便的 **客户端** [#]_，它包含了一个命令行工具和一个 WebUI，该UI界面运行在计算机本地 http://localhost:8180。Parity 由 Rust 语言编写并且开源，开发者是以太坊基金会的几个创始会员，以太坊的黄皮书作者 Gavin Wood 博士就是其中之一。

   该客户端的一大特色就是启动速度快，支持命令行工具，当初始化网络下载区块链数据时较为顺畅，相比于 Geth 更加注重性能体验。

.. figure:: /img/Picture11.png
   :align: center
   :width: 600 px

   Parity客户端账户总览页面


.. topic::  Mist

   运行环境：Windows/Linux/Mac

   官方推荐的图形化界面全节点钱包，技术实力雄厚，已经开源，成为实质上的官方钱包桌面版 **应用程序** [#]_ 。该钱包的优点是自身就是一个完整同步区块链的节点，当广播交易时，不需要通过额外的服务器中转，发送给自身即可。该钱包自带区块链浏览功能，方便在图形界面中找到用户关心的地址、关心的区块、想调用的智能合约。缺点是因为同步的是全部区块链数据，需要用户自网络下载接近1TB 的数据（截至2018年7月），需要几天的时间才能同步完毕。并非普通轻度使用的用户的首选。

.. figure:: /img/Picture12.png
   :align: center
   :width: 600 px

   Mist客户端账户总览界面


.. topic:: MyEtherWallet

   运行环境：Chrome/Firefox/Safari网页浏览器

   以太坊社区受欢迎的轻量级开源 **网页钱包** [#]_ 。前端网页代码完全在浏览器中执行。可以在线创建账户、接收发送以太币、下载 keystore以供离线存储、具备智能合约相关功能。由于只在网页前端运行，在浏览器关闭后并不会替用户持久保存私钥，所以还要用户自行妥善下载私钥来保存。因为网页钱包始终需要用户联网使用，存在一定的私钥泄漏的安全风险。由于该网站实在太出名，针对它的钓鱼网站层出不穷，不少用户在假网站上输入私钥而被黑客窃取了以太币。在使用该网站之前，请务必检查你访问的是否为MyEtherWallet的正确网址，且确认网络防火墙软件已经开启防护。

.. figure:: /img/Picture13.png
   :align: center
   :width: 600 px

   MyEtherWallet 在浏览器中运行时的界面


.. topic:: MetaMask

   运行环境：Chrome

   这是一款Chrome 电脑插件 [#]_，可以运行在 Chrome 浏览器中。它是一个值得推荐的的钱包。它的优点是可以自动在浏览器页面中注入 ``web3.js`` 的Object实例，这样网页应用 DApp 需要读取以太坊区块链数据，或者需要账户授权签名的时候，MetaMask 会自动提示客户签名并执行发送交易。
   它支持许多符合 ERC20格式智能合约的币种，有丰富的多账户管理体系。它的缺点是不易获取和安装，国内用户需要连接Google Chrome 官方商店才能下载这款插件。


.. figure:: /img/Picture14.png
   :align: center
   :width: 600 px

   Metamask的界面


.. topic:: imToken

   运行环境：安卓/苹果手机

   国内团队打造的手机 App 应用。客服沟通效率高，支持的以太坊 ERC20格式智能合约代币非常丰富。已经推出了1.0版本，现在正逐步推出2.0版本。操作简单，容易上手。当用户转账时，通过imToken的服务器节点进行交易广播。它的源代码曾是闭源的 [#]_，公信力不如前述几家强。

.. figure:: /img/Picture15.png
   :align: center
   :width: 600 px

   imToken在苹果手机上的界面


.. [#] 笔者注：助记词，即为用12或者24个单词来帮助记忆私钥的方法。
.. [#] 笔者注：源代码地址https://github.com/ethereum/go-ethereum
.. [#] 笔者注：源代码地址https://github.com/paritytech/parity-ethereum
.. [#] 笔者注：源代码地址https://github.com/ethereum/mist
.. [#] 笔者注：源代码地址https://www.myetherwallet.com
.. [#] 笔者注：源代码地址https://metamask.io/
.. [#] 笔者注：2018年10月24日，imToken宣布TokenCore核心代码开源。