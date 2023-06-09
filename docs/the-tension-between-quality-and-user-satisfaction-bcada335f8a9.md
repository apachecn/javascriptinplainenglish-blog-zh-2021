# 质量和用户满意度之间的矛盾

> 原文：<https://javascript.plainenglish.io/the-tension-between-quality-and-user-satisfaction-bcada335f8a9?source=collection_archive---------20----------------------->

软件工匠非常关心他们工作的质量，但是商业现实通常更重要。

作为一名软件设计师，你经常会面临以下难题:如何交付尽可能好的质量结果，从而满足你的设计师，同时取悦终端用户，他们通常昨天就想要高质量的结果？

让我们一起来探讨这个话题。这个内容是我的 [Dev 概念系列丛书](https://dev-concepts.dev)的[第一卷](https://gum.co/DevConcepts-Part-01-SoftwareCraft)的一部分。

![](img/4ac3391db98ad09bb16a48c48f730231.png)

# 权衡和责任

这是一个平衡的问题。软件设计师通常应该努力追求更好的质量，但是总要做出权衡。满足用户需求和尊重硬性期限永远是优先的，但这并不意味着你应该永远放弃质量。

作为专业人士，你应该敢于质疑商业选择和期限。你还应该提供信息，并带来清晰度。您的客户应该知道他们的选择，其中涉及的权衡，并需要被引导到更好的选择。此外，质量也与用户满意度密切相关，即使这并不总是显而易见的。

# 软件质量方面

软件质量由外部*和内部*两个要素组成。对于最终用户来说，外部质量通常更加有形。例如，系统的用户只能看到用户界面及其行为。如果用户界面的质量下降，那么它会很快被发现。内部质量与系统的*健壮性*及其*可靠性*更有关系。

如果你在内部质量上偷工减料，那么它也会影响最终用户，但是以不同的和看起来不太明显的方式。他们会得到不正确的结果，或者计算会花费比预期更长的时间，等等。系统可能会意外崩溃，缺陷率可能会急剧增加。随着时间的推移，交付新功能可能需要越来越长的时间，因为越来越多的时间花在了修复漏洞和灭火上。最重要的是，快速和肮脏有时会给企业带来巨大的后果(如声誉和财务)。

# 高期望

有趣的是，我们对 IT 系统的期望很大程度上受到我们日常生活中使用的应用程序的影响(例如，Gmail、Office 365 等)。这转化为客户的高期望，他们不理解(或不关心此事！)关于实现与世界上最大的组织相同的结果的复杂性。你很可能不是在为谷歌、微软、脸书、亚马逊、苹果等公司工作。这意味着您可以支配的资源有限，技能各异，而且显然需要做出权衡。确保告知客户他们要求的复杂性，并让他们“回到现实”。

# 质量和成本之间的持续紧张

我们都习惯了质量与成本的关系。通常在现实生活中，如果我们付出的越少，我们得到的质量就越差，反之亦然。软件不一定如此。总是有灰色的阴影。让我们再考虑几个维度，以便更好地理解可能的解决方案:

如这张精彩的“花图”所示(没错，就是瞎编的)，有几个密切相关的概念:

*   范围:我们可以决定开发更少的功能，或者简化项目路线图上的功能
*   **时间**:我们可以改变时间表，以便能够在交付预期特性的同时达到所需的质量水平
*   **质量**:我们可以决定做出质量折衷，从而在保持最初时间表的同时降低(直接)成本
*   风险:我们可以接受承担更多的风险

无论您选择哪种方法，*所有的*尺寸都会受到影响。例如，在保持相同范围的情况下，减少 10 个可用时间将很可能对质量(和项目风险)产生灾难性的影响。降低质量会增加风险，增加完工时间，从而增加总成本，等等。

清晰及时的沟通是成功的关键。在决定降低内部或外部质量以满足最后期限之前，确保理解可能的权衡，并向利益相关者解释这些，以便企业可以做出有意识的决定。一个[优势、劣势、机会、威胁(SWOT)](https://en.wikipedia.org/wiki/SWOT_analysis) 分析对此很有用。

注意:作为一个软件工匠，你也应该在需要的时候“战斗”,这样质量就会被考虑进去，成为项目计划的一部分，就像其他的考虑一样。例如，如果有代码改进/清理要处理，那么您应该证明并维护它们。永远不要对质量和安全风险保持沉默。

帮助最终用户认识到质量还不够完美的一个方法是减少用户界面的修饰。这个想法是，如果你交付了一个顶级的用户界面，那么用户会觉得他们已经收到了完整的&高质量的软件，而不管它的内部是什么。

参考资料:

*   [SWOT 分析](https://en.wikipedia.org/wiki/SWOT_analysis)
*   [马丁·福勒的可交易质量假说](https://www.martinfowler.com/bliki/TradableQualityHypothesis.html)
*   [杰克·坎帕内拉《质量成本原理、实施和使用》](https://www.amazon.com/Principles-Quality-Costs-Implementation-Use/dp/087389443X?tag=dsebastien00-20)

# 结论

在本文中，我快速探索了围绕软件质量和用户满意度的不同权衡。这是一场艰难的辩论，因为现实是复杂的，每种情况都是特定的。我的主要观点是，你不应该总是为了赶上最后期限而偷工减料，降低工作质量。有时候，最好站出来，分析利弊、相关风险，并帮助你的客户做出日后不会后悔的决定。

你对这个话题有什么看法？你如何应对交付的压力以及由此产生的紧张？

今天到此为止！

PS:如果你想了解大量关于产品/软件/Web 开发的其他很酷的事情，那么[订阅我的时事通讯](https://dsebastien.net/news)，[查看 Dev Concepts 系列丛书](https://dev-concepts.dev)，[加入软件工匠社区](https://join.slack.com/t/softwarecrafterstalk/shared_invite/zt-umgx3v06-4rtJ20PXz867GTPzCk1zeQ)，并且[来 Twitter 上打招呼吧！](https://twitter.com/dSebastien)

*原载于 2021 年 9 月 3 日 https://dsebastien.net*[](https://dsebastien.net/blog/2021-09-03-quality-vs-user-satisfaction)**。**