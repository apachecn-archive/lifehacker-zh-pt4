# 我是布莱恩·穆勒，这是胡萝卜加大棒背后的故事

> 原文:[https://life hacker . com/im-Brian-mueller-and-this-is-the-story-behind-carrot-1454800997](https://lifehacker.com/im-brian-mueller-and-this-is-the-story-behind-carrot-1454800997)

胡萝卜不是你的普通待办事项经理。它的创造者 [布莱恩·穆勒](https://twitter.com/brianmueller333) 将其描述为“有个性的待办事项清单”， [该应用](https://itunes.apple.com/us/app/carrot-to-do/id591840203) 将你的清单变成一个 [略带虐待狂的](https://lifehacker.com/carrot-turns-your-to-do-list-into-a-slightly-sadistic-g-5978354) 游戏，由一个只会在你完成任务后才会高兴的机器人主人完成。(胡萝卜最近推出的 [闹钟](http://lifehacker.com/carrot-alarm-turns-your-morning-routine-into-a-sadistic-1140607638) 也是如此，它让你完成一系列任务来关闭它。邪恶？也许吧。才华横溢？绝对的。)我们采访了 Brian，以了解胡萝卜背后的灵感、他一路走来遇到的问题以及他对其他新手开发者的建议。

Watch

#### 胡萝卜的创意来自哪里？你是在试图解决你经历过的问题，还是灵感来自其他地方？

理论上，让我的生活有条理的想法一直很吸引我。我会对开始某个大项目感到兴奋，下载最新最棒的待办事项应用程序，然后当我实际进入所有任务时，却碰了壁。这些应用程序总是过于复杂、乏味、无趣，以至于更新它们本身就是一件苦差事。我的 iPhone 成了生产力应用程序死亡的墓地。我最后问自己，“为什么没有人列出一个我真正想用的待办事项清单？”我需要的是一种激励:某种能让我从清单上划掉任务变得如此有趣，以至于我真的很期待去做的东西。

我的第一反应是添加点数和徽章，我可以通过完成任务获得这些点数和徽章——典型的游戏化费用——但我越想越意识到解锁一些愚蠢的徽章不会让我的家务变得更有趣。当我玩游戏时，我不是为了拿高分而玩的。我是为了写作、角色和故事而演奏。我回来的原因是想知道接下来会发生什么。在我做出这个飞跃之后，这个想法开始变得清晰起来。应用程序的核心是一个角色——这个有趣/讽刺/虐待狂的人工智能，名叫胡萝卜。她几乎就像一个虚拟宠物，这个邪恶的超级计算机，你必须通过在现实生活中完成事情来保持快乐。如果你成功且高效，她会奖励你。但是，如果你偷懒，她会生气的。会有一个围绕胡萝卜给你的宠物猫的中心故事；随着你使用这个应用程序，故事会一点一点地被揭示出来，并根据她对你是高兴还是生气而变化。我所设想的比我见过的任何其他“游戏化”系统都更像游戏。

#### 你想出这个主意后，下一步是什么？

在开始写胡萝卜之前，我实际上从来没有规划过一天的生活——我上学是为了成为一名作家。所以第一步应该是:“雇人来为我设计和编码。”

但在这之前，我抓起了一本关于 iOS 编程的书，想浏览一下，学习一些词汇，这样我在找程序员时就不会听起来像个白痴。令人惊讶的是，前几章并没有那么难，所以我坚持读完了整本书。这很费时间，但是这些概念远没有我想象的那么难理解。

所以我没有雇佣程序员，而是决定自己写这个应用。我通过阅读苹果的文档和在 [Stack Overflow](http://lifehacker.com/crowdhacker) 等网站上的帖子，弄清楚了如何完成应用程序的每个主要部分(输入任务、保存任务等等)。1.0 版本从开始到结束大概用了一个月的时间。代码库不一定漂亮，但我发挥了我的优势——也就是我的写作背景——通过将大量的个性和极客幽默注入到应用程序核心的虐待狂机器人角色中。

#### 你如何选择目标平台，忽略或等待哪些平台？

这对我来说是一个容易的决定。我刚起步时规模很小，没有任何经验，所以这意味着我只能瞄准一个平台。我已经有了一部 iPhone，并且听说为 iOS 开发一个应用程序比其他平台更容易，所以我决定走阻力最小的路。现在胡萝卜变得非常受欢迎，是否扩展到其他平台的问题是一个开放的问题，我将继续探索，但作为一个独立的开发者，我也必须担心自己太分散。

#### 你最大的障碍是什么，你是如何克服的？

胡萝卜的 1.0 版本在实际功能方面非常简单——只需下拉添加一个任务，向右滑动即可完成。就这样。胡萝卜推出后，我不可避免地收到了一堆胡萝卜用户的功能请求。"胡萝卜很可爱，但为什么我看不到我已完成的任务？"“我爱上了胡萝卜，但我需要能够编辑任务，然后才能向她求婚！”“我有兴趣崇拜胡萝卜作为我的新上帝。但首先，我要预产期！”我尝试了一堆不同的用户界面模型，但我就是找不到一种方法来添加所有这些额外的功能而不损害胡萝卜的极简设计。直到我回到游戏中寻找灵感。当你玩一个游戏时，你开始时只有一两个基本能力。一旦你习惯了旧的游戏，新的游戏会在游戏过程中出现。同样的想法很容易被带到胡萝卜身上:你开始时有能力创建和完成任务，然后当你在现实生活中踢屁股并在她的游戏中升级时，你会解锁其他功能，如到期日或 Siri 集成。解决这个设计问题最终让人们比以往任何时候都更加投入到胡萝卜中。他们不再是被动的使用者；相反，他们的行动积极地使胡萝卜成为一个更好的应用程序。

#### 对你来说，发射是什么样的？

从一开始，胡萝卜的设计就迎合了我自己的怪癖。我严重怀疑其他人会喜欢这个应用程序——我可能会从朋友和家人那里下载 30 次，仅此而已。我第一天都没拿到那么多。然而，在第二天，当 Lifehacker 推出胡萝卜时，下载量开始上升。从那以后，随着媒体越来越多的报道，苹果的功能出现在 App Store 中，我也付出了很多努力，用新的内容和功能来保持应用的新鲜感。当她达到 1000 次下载时，我认为这真的很酷；令我震惊的是，她现在成千上万了。很高兴看到胡萝卜并不像许多应用程序一样，在发布时大受欢迎，但很快就销声匿迹了。事实上，在 1.0 版本发布几个月后，上周她迎来了人生中最重要的一天。

但是最好的部分是用户的反馈。当我开始听说胡萝卜是他们实际上一直使用的第一个待办事项清单时，我知道我在如此不同的方向上做了正确的选择。收到来自人们的电子邮件，说你创造的东西实际上改变了他们的生活，这很令人羞愧。

#### 你如何有效地处理用户的要求和批评？

胡萝卜的用户很神奇。他们的电子邮件和推文几乎总是针对这个角色，而不是我。他们与她进行完整的对话，询问他们是否可以娶她，炫耀他们自制的视觉传感器针，等等。胡萝卜对他们来说不仅仅是一张待办事项清单。

对我来说，与我的用户保持紧密联系很重要。即使我在忙着做其他事情，我也会优先考虑快速而周到地回应反馈。当我们出去吃饭时，这让我的妻子很恼火，但是胡萝卜的一些最好的和最独特的特点已经从这些讨论中产生了，所以这是值得努力的。

批评有时可能很难听到，但它们通常很有帮助。例如，在《胡萝卜》的第一版中，如果你没有在 3 个小时内完成任务，她会对你发火。我认为这完全符合胡萝卜的性格，她会生气，你决定去睡觉，而不是做更多的事情。但早期用户是对的，这个窗口太小了——不得不不断地微观管理她的情绪是令人讨厌的。如果我没有马上听他们的，胡萝卜的观众可能会少得多。

#### 现在，如何在开发新功能和管理现有功能之间分配时间？

这是一个很难回答的问题，因为胡萝卜和所有的待办事项都不一样。我不断发现自己被拉向两个方向:要么我可以添加新的“有用”功能来改善实际的待办事项列表，要么我可以添加新的“有趣”内容来扩展用户对应用程序的享受。

例如，没有人会要求在他们的待办事项中加入一只虚拟宠物猫。当然，我花在设计和编码上的时间并没有增加更多有用的功能，但是我的用户绝对喜欢那只该死的猫。他们继续使用胡萝卜——结果在现实生活中完成了更多的事情——因为他们不想让“络腮胡”船长挨饿。最终，添加这个荒谬的功能比添加一大堆专注于生产力的功能更能提高人们的生产力。这让我非常高兴。

所以最后，我试着在每个主要版本中加入一些东西:bug 修复、常识性的新特性和 bugnuts 疯狂的内容。

#### 你会给那些想从事类似项目的人什么建议？

从小处着手。在《胡萝卜》之前，我倾向于构思雄心勃勃的项目，比如一部史诗般的 600 页的时间旅行小说，这将需要数年时间才能完成。问题是，很难保持这么长时间的动力，尤其是如果你独自工作的话。你将能够克服你遇到的第一个障碍，但当你开始意识到面前有这座不可逾越的工作之山时，它会变得越来越难。更糟糕的是，你心里清楚，即使你创造了奇迹，完成了那件该死的事情，它也很有可能砰的一声落地，你花的所有时间都白费了。放弃变得太容易了。

改掉这个习惯并不容易。我不得不强迫自己选择一个小项目，一个可以在几周内完成的项目。我不得不抑制住继续增加新功能的冲动。我不得不告诉自己，最终的结果是“足够好”这可能是我曾经不得不做的最困难的事情之一，但是我的一些最好的想法是从这些限制中产生的。例如，《胡萝卜》中的主角原本是一只高傲的柯基犬，戴着礼帽、单片眼镜和领结，名叫威化夫爵士。感谢上帝，我没有足够的时间来弄清楚如何做他的角色动画，否则我永远不会满足于一个由四个同心圆组成的讽刺机器人角色。

<small></small>*[<small>*App 背后*</small>](http://lifehacker.com/behindtheapp) <small>*让我们深入了解一些我们最喜欢的应用是如何诞生的——从创意到发布(以及之后)。有你想看到的人吗？邮箱*</small> [<small>*泰莎*</small>](https://mail.google.com/mail/?view=cm&fs=1&tf=1&to=tessa@lifehacker.com) <small>*。*</small>*

**<small>这篇文章是我们的</small>* [*<small>恶周</small>*](https://lifehacker.com/welcome-to-lifehackers-fourth-annual-evil-week-1453143089) *<small>系列的一部分，在这里我们看到了做事的阴暗面。知道邪恶意味着知道如何打败它，所以你可以用你的邪恶力量做好事。想要更多吗？查看我们的</small>* [*<small>恶周标签页</small>*](http://lifehacker.com/tag/evilweek) *<small>。</small>**