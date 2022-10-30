# 应用背后:LastPass 的故事

> 原文:[https://life hacker . com/behind-the-app-the-story-of-lastpass-1669310481](https://lifehacker.com/behind-the-app-the-story-of-lastpass-1669310481)

使用安全、复杂的密码非常不方便，因为最安全的密码 [是那些你不记得的](https://lifehacker.com/the-only-secure-password-is-the-one-you-can-t-remember-5785420) 。随着引人注目的安全漏洞变得司空见惯，许多人都在寻找安全管理其密码的解决方案。像 [LastPass](http://lifehacker.com/the-intermediate-guide-to-mastering-passwords-with-last-5645162) 。

Watch

[LastPass](https://lastpass.com/about-lastpass) 就是从这样的需求中诞生的，正如 [乔西格里斯特和他的联合创始人](https://lastpass.com/about-lastpass) 出于需要，需要一种管理自己密码的方法。他们着手创建一个管理随机生成的安全密码的平台，不管你何时何地需要登录你的网站。这项服务已经发展了多年，可以在 LastPass 团队管理的尽可能多的平台上使用，并且为了用户的利益继续升级安全措施。我们与 Joe 进行了交谈，以了解更多关于这一切是如何结合在一起的，以及他们如何管理自己的进度。

#### 这项服务的想法来自哪里？你是在试图解决你经历过的问题，还是灵感来自其他地方？

LastPass 首席执行官乔·西格里斯特:在我们自己遇到密码问题后，四名开发人员成立了 LastPass。用我们认为安全的方式做这件事太复杂了。当时我们使用的是加密文件，但解密、设置密码、在添加新密码的情况下再次加密文件、保持文件同步、查找数据非常痛苦...做对了就是一塌糊涂。

当我们开始询问人们做了什么时，我们一致听到两种回答:

1.  "我在任何地方都重复使用同一个密码的变体."
2.  “我有一个‘分层’密码方法(一些帐户使用‘一次性’密码，更重要的帐户使用稍微强一点的密码，银行和金融帐户使用一个‘强’密码)。”

这两种方式都有风险，也不可持续。我们知道我们面临的问题只会越来越严重。

#### 你想出这个主意后，下一步是什么？

我们成立了公司并开始工作！我们之前在一家名为 eStara 的初创公司运营了一家云服务公司八年。我们知道我们想要一个具有本地备份和本地加密的基于云的应用程序的便利性，消除使用云的两个典型缺点:没有本地访问，以及云供应商能够访问您的数据。

#### 你如何选择目标平台，忽略或等待哪些平台？

普及从一开始就是我们的优先事项。我们希望每个人都能够访问他们的密码和其他存储的信息，无论他们在工作时、在家里还是在路上使用什么。我们从当时的主要平台(Mac、Windows、Linux)和浏览器(Internet Explorer 和 Firefox)开始。

当我们开始的时候，情况要简单得多。iOS 1.0 版本甚至还不允许外部开发者上传应用！

#### 你最大的障碍是什么，你是如何克服的？

第一年我们花了大量时间进行教育。我们在线和离线交谈的每个人都对基于云的密码管理器持怀疑态度，并质疑我们的解决方案。他们不信任这项服务的本能是因为，在 LastPass 问世之前，云中的所有数据都容易受到黑客和流氓雇员的攻击。一旦人们明白我们是用一个永远不会接触到我们的服务器的密钥在本地加密数据，就会发出“啊哈！”我们开始建立一个接受并使用 LastPass 的社区。

#### 对你来说，发射是什么样的？

我们的测试版发布既令人兴奋又充满压力:昼夜不停地观察和回应试用我们产品的人。如果你查看 2008 年 8 月底和 9 月初的帖子，你仍然可以在我们的论坛上看到相当多的那段时间的帖子。人们喜欢这个产品，但是怀疑我们是谁，怀疑他们是否能信任我们。我们犯了错误，但我们对此保持透明和坦率，这也有助于赢得我们社区的信任。

#### 你如何有效地处理用户的要求和批评？

多年来，我们的社区对我们来说一直是一个重要的反馈环，我们一直积极地监控电子邮件(以及后来的票务系统)、博客、Twitter、脸书、论坛和其他在线中心的评论。对于我们来说，这是一个很好的温度检测，可以看到我们的用户对这项服务的感受，以及他们在自己的圈子里如何谈论 LastPass。

一开始，我亲自阅读了所有的支持邮件，尽管这在几年后变得不可持续。相对于我们用户群的规模，我们保持了一个小而专注的支持团队，处理客户错误报告、反馈和功能请求。

评估用户认为下一步应该做什么或者应该开发什么功能更加困难。我们经常发现，他们很擅长告诉我们目前什么是可行的，什么是不可行的，但要推进服务，最好依靠我们在行业中的经验，我们如何看待空间的发展，以及我们的直觉。

#### 现在，如何在开发新功能和管理现有功能之间分配时间？

在任何时候，我们都有十几个平台需要关注。每当有重大的新版本发布时，比如 Mac OS X Yosemite 或 Android 的新 Lollipop，我们都必须了解它会如何影响我们的产品，是否可能有任何新功能，以及我们如何利用平台的进步来改善我们的用户服务。我们希望尽可能在发布日准备好我们的服务。如果有些事情不尽如人意，我们有一个强大的社区，可以立即向我们提供宝贵的反馈，以便我们做出改进。

由于我们为团队提供了一个消费产品和[LastPass Enterprise](https://lastpass.com/enterprise_overview.php)，我们还必须为两个非常不同的社区开发产品，并了解每个社区如何使用产品。

我们还必须关注身份认证技术和网络安全的整体情况。随着形势的变化，我们必须将我们的服务导向能够为用户提供最大价值的地方。这是一个很难达到的平衡，但却是至关重要的。

#### 你会给那些想从事类似项目的人什么建议？

从小处着手:一旦你有了任何一群人都想用的东西，是时候发布了。尽早关注吸引力:获得一个使用你的产品并与你持续沟通的核心群体。用户反馈很重要，但是要小心不要让它分散你的注意力。保持热情，记住“一夜成功”需要多年。

* * *

<small></small>*[<small>*App 背后*</small>](http://lifehacker.com/behindtheapp) <small>*让我们深入了解一些我们最喜欢的应用是如何诞生的——从创意到发布(以及之后)。有你想看到的人吗？邮箱*</small> [<small>*安迪*</small>](mailto:andy@lifehacker.com) <small>*。*</small>*