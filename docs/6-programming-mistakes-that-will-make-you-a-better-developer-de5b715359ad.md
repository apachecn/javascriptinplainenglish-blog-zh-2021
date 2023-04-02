# 6 个让你成为更好的开发者的编程错误

> 原文：<https://javascript.plainenglish.io/6-programming-mistakes-that-will-make-you-a-better-developer-de5b715359ad?source=collection_archive---------15----------------------->

## 如果你回避它们，你永远也学不会变得更好。

![](img/5ec3f0005586ace1d54c4ccfcba58c55.png)

Photo by [krakenimages](https://unsplash.com/@krakenimages?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

编程是这样一种职业，在这种职业中，学习不会随着大学考试和论文、工程或学士论文答辩而结束。

程序员每天都在学习，或者如果他们想在职业生涯中取得更多成就，至少他们应该这样做。但是，我们不可能在课程、研究和其他网络研讨会上学到所有的东西。

事实上，我们通过从错误中学习获得的大部分硬技能——当然，如果有人提前告诉我们，或者我们只是得出结论说我们做错了什么。

今天，我想向大家介绍一些年轻但年龄稍大的程序员经常犯的错误。许多问题是可以避免的，这将显著提高代码的质量，并避免不断增加的技术债务。

# **1。代码审查是一个学习的机会。**

所有的错误都应该在代码审查期间被发现。所谓的代码审查。它们应该是，但并不总是如此——原因各不相同。缺乏时间、意志、能力等等。

对于年轻的程序员和那些有更多经验的人来说，这是成为更好的开发人员的最好方法。从错误中学习是人生最好的学校。

组织良好的代码审查不仅对代码作者有益。对于团队来说，它主要是一种工具，可以及时了解项目中正在发生的事情，还可以最小化技术债务的出现。

忽视这一点会导致可怕的后果。说到他们，即使一天是 48 小时，我保证也没有足够的时间去扑灭接二连三发生的火灾。我个人不喜欢卷入这样的事情。

# **2。不要把方法做得太大。**

没有什么比在给定的应用程序中处理 1501900 个功能的大方法更糟糕的了。我甚至不希望我最大的敌人保持这样的准则。

任何改变，比如以一个新图标的形式添加一个简单的修改，都将是如此之长，以至于你的项目经理会因为你的懒惰而将你赶出工作岗位，而你将没有时间做任何事情。因此，总是试图创建尽可能简洁的代码，这些代码也可以在其他项目组件中使用。

# **3。不要让你的控制器太大。**

继续上一点的想法，对于过大的控制器也是如此。

编写代码时，遵循 SoC 原则(问题分离)是值得的。作为程序员，让我们时不时地扮演一下测试人员的角色，努力让他们的工作变得更轻松。对了，我们也会自助。

当我们的项目稍微大一点的时候，当一切都井然有序的时候，工作起来会容易得多。然而，有时开发的应用程序达到这样的规模，QA 团队修复检测到的 bug 所需的时间是 7 小时搜索代码中的给定片段，30 分钟的修正，以及 30 分钟测试修复是否有效。

# **4。“明智地”选择设计模式**

设计模式是一个非常酷的“发明”使用它们是值得的，但应该深思熟虑，可以理解。例如，当编写一个移动应用程序时，不要使用经典版本的 MVC —因为它是已知的和喜欢的—但是让我们想一想。

在这个特殊的例子中，使用这样的体系结构是一种尝试。那么，如果我们的应用程序在数据管理方面存在问题，而我们自己也在不断地与各种奇怪的事情“斗争”,那么如果我们使用一个很酷且流行的架构模式会怎么样呢？

在这种情况下，一个更好的解决方案可能是使用 MVVM 模式或稍微修改的 MVC 版本。深思熟虑地、可以理解地选择设计和架构模式。做得好的决策会促成很多事情，极端情况下糟糕的决策甚至会导致项目崩溃。

# **5。简单的解决方案是最好的。**

这个建议是显而易见的，但是值得写下来。第一，千万不要强行把事情复杂化！如果你有一个简单的任务，比如实现一个用 n 进行强计算的函数，那就尽可能简单地去做。

例如，使用递归。如果你想让你的代码“更好”和更短——当然，你可以这样做，并应用函数式编程范式，即 lambda 表达式。然而，在此之前，问自己一个重要的问题。这对你有什么好处？如果答案是“更短的代码和对勇敢者的尊重”，那么就让它去吧。尽可能简单。另一件事是，由于各种原因，如果使用 lambdas 编写的相同结构比基于递归或迭代循环的解决方案运行得更快。有意识地做出这样的决定是的，

# **6。记得那些测试。**

当你创建代码时，很容易出错。例如，您可能会误解客户端需求，错误处理用户输入，或者管理内存不充分。有很多种可能。我甚至会说，它是一个无限集合。那我该怎么修呢？这个问题的答案就是一个词——测试。

但是，请记住，即使有 100%的代码覆盖率，我们也不能保证所有的 bug 都会被消除。因此，在进行软件测试时，使用适当的技术和方法是值得的。

所有此类活动都应以结构化和正规化的方式进行。如果你对这种情况有任何疑问，你总是可以利用自由软件审计，以及作为最后的手段，将彻底分析项目的所有方面的其他外部服务。

# **总结**

在今天的文章中，我介绍了一些在软件开发过程中犯的有趣的错误。这种情况值得避免，但是请记住，我们永远不会避免所有的情况。

确保软件由合适的测试团队在持续的基础上进行测试是值得的。可能有必要使用审计来回答代码处于什么状态？愿这永远不会发生在你身上。然而，避免它并不像看起来那么困难。

*更多内容尽在*[***plain English . io***](http://plainenglish.io/)