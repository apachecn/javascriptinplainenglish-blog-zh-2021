# 创业公司爱 Node.js 的 5 个理由

> 原文：<https://javascript.plainenglish.io/5-reasons-why-startups-love-node-js-92a7c6243117?source=collection_archive---------18----------------------->

![](img/5b8ca18d091fb89facbc3cf18edd48f6.png)

创业的定义有很多。有的强调其规模，有的创新；然而，所有初创公司的普遍定义元素是它们的快速增长。

像这样的公司有一个共同的目标——快速增长。其他一切似乎都无关紧要，因为这些公司甚至可能连续多年亏损(想到一家叫车巨头)——盈利(目前)还不是他们的目标。因为就是这样，创业公司的财务跑道有限。

因此，初创公司的工程团队需要一种语言和环境，使他们能够快速迭代，同时保持低成本。

![](img/5f168bd29ef5a233dfb55dc1cba2d6d6.png)

# 闪电很快

## 发展

在快速增长的世界里，有一个关键术语——最小可行产品或 MVP。

这是什么？它是以获得顾客关注为目的的具有基本特征的服务或产品的创造。因此，更高级的功能应该是随着时间的推移而开发的，因此被省略了。最重要的是，可能会出现产品不太适合市场的情况，这意味着公司将不得不转向。

快速发展的公司越来越多地将 JavaScript 与 TypeScript 结合起来。它们不仅在使用[正确的测试方法](https://www.itmagination.com/blog/qaops-in-the-agile-age-using-automated-manual-testing)时没有问题——它们还能让公司比使用其他流行语言更快地编写代码。我们已经提到[PayPal 对他们团队将后端从 Java 迁移到 JavaScript](https://www.itmagination.com/blog/node-js-changed-corporate-software-engineering) 的开发速度惊叹不已。简而言之，他们不仅花了更少的时间来编写相同的函数，而且用了更少的代码行。这件事发生在打字稿之前。想象一下，如果现在发生同样的转变，结果会怎样！

此外，部署到生产环境也很简单，因为您不需要编译代码库。也不需要设置单独的 web 服务器，比如 Apache。你上传代码，你旋起 [PM2](https://www.npmjs.com/package/pm2) (生产流程经理；帮助管理应用程序)，您就可以开始工作了。

## 表演

Node.js 很快。有多快？在 [TechEmpower 基准测试](https://www.techempower.com/benchmarks/#section=data-r20&hw=ph&test=composite)中，JavaScript 与[“just-js”并列第二](https://github.com/TechEmpower/FrameworkBenchmarks/tree/master/frameworks/JavaScript/just)当然，这个项目本身有点让人好奇，尽管这个应用当然可以工作。比用 C++写的 drogon，用 Rust 写的 ntex 或者 actix 都快[原文如此！].

[Es4x](https://reactiverse.io/es4x/) 排在第 18 位，而 [Fastify](https://www.fastify.io/) 排在第 58 位。这两个都是 JavaScript 框架——后者是我提到的所有三个 JS 框架中最受欢迎的，例如微软选择了它。

# 它是高度可扩展的

有三种主要方法来扩展应用程序:

## 1.克隆

当你让同一个应用程序的每个克隆体处理一些工作时。这是最简单的方法，而且非常有效

## 2.分解

它是将一个应用程序分解成多个更小的应用程序来完成相同工作的实践。[该术语通常与微服务相关联。](https://www.itmagination.com/blog/node-js-changed-corporate-software-engineering)

## 3.剧烈的

你希望应用程序的每个克隆只处理一部分数据，然后你拆分应用程序。例如，每个克隆将根据用户的位置或语言来照顾他们。

回到 node . js——它是可伸缩性之王。运行时的作者非常强调用 Node.js 编写的应用程序的增长能力。这是这段代码的核心特性，甚至是它大力推广的特性之一。在项目的 about 页面上，第一句话，我们可以读到“[……]node . js 旨在构建可扩展的网络应用。”

它的一个内置模块[“集群”](https://nodejs.org/api/cluster.html)，提供了一种利用您机器上所有处理器内核的现成方法。是的，尽管 JavaScript 无法使用多于 1 个内核！

因此，利用单台服务器的所有资源非常容易。它的工作方式是将主应用程序拆分到几个相关的进程中，这些进程使用进程间通信与主应用程序进行通信。如果您对消息传递的确切工作方式感兴趣，请阅读[节点的](https://nodejs.org/api/process.html#process_process_send_message_sendhandle_options_callback)文档。

不仅克隆容易——毕竟 JavaScript 是微服务的霸主之一。对于扩展 Node.js 应用程序的所有复杂性，[这篇文章是一个很好的资源](https://www.freecodecamp.org/news/scaling-node-js-applications-8492bd8afadc/)。

# 它在前端和后端都使用 JavaScript

维持两个独立的团队成本很高。创业公司有很多资产——尽管多余的钱通常不在其中。因此，许多快速成长的新公司选择在后端和前端使用 Node.js。Node.js 的选择一点也不差。

浏览器只能执行 JavaScript 也是最自然的选择——[从技术上来说，你可以使用其他语言来增加网页的交互性](https://webassembly.org/)，尽管现在还为时过早。因此，如果你想在任何地方使用同一种语言，你必须在前端和后端都使用 JavaScript。

这样，团队更小，更敏捷，沟通更好。

# 大量候选人——超过 1300 万人

在招聘 JavaScript 开发人员时，你可以期待一个广泛的人才库。大约有 1380 万人，这是世界上最高的数字。这个数字也在增加。去年 10 月(2020 年 10 月)，这一数字为 1240 万。

因为这种语言的学习曲线比较平缓，所以速度不太可能会慢下来。除非发生重大的世界灾难，否则事情不会改变——这就是为什么以 JavaScript 为中心规划未来既不短视也不不负责任。这是一项安全的投资。

# 超过 150 万个第三方包

JS 社区有个游戏。选择一个单词并检查是否存在具有给定名称的 npm 包。当然，不完全是字面上的意思——关键是软件包的广度是前所未有的，非同寻常的。对于创业公司来说，这意味着在现成的解决方案方面有一个安全网。组件、库、包、模块——你需要的任何东西都在那里。事实上，2020 年 4 月，[他们有 130 多万！](https://web.archive.org/web/20210615160143/https:/blog.npmjs.org/post/615388323067854848/so-long-and-thanks-for-all-the-packages.html)

包管理器也使安装变得轻而易举——无论是在本地场景中还是在例如容器中。如果您不喜欢这个特定的解决方案，请不要担心。您可以随意使用[纱线](https://yarnpkg.com/)和 [pnpm](https://pnpm.io/) 。

# 有没有我不想使用 JavaScript 的时候？

Node.js 速度惊人，使用的资源很少，是未来的证明。有没有什么时候你不想用它的？

是的。JavaScript 并不总是一个好的选择。例如，如果您运行一个为嵌入式设备或机器学习开发软件的初创公司，那么您可能需要重新考虑为您的核心产品选择 JavaScript。在这里，即使过了这么多年，C 和 C++仍然是关键。同样，在游戏开发的世界里，你不会看到游戏是用任何动态语言开发的。

不过，这些都是高度专业化的领域，因此，如果你属于 95%的商人，Brendan Eich 创造的语言总是初创公司的一个好选择。

***附言:我们正在招聘 Node.js 开发者！*** *对于所有的 Node.js 专业人士，我们有好消息——我们正在招聘。无论您是* [*后端开发人员*](https://www.itmagination.com/open-jobs/NodejsDeveloper-8050000012856481) *、* [*反应开发人员*](https://www.itmagination.com/open-jobs/ReactDeveloper-8050000012874788) *、* [*反应本地开发人员*](https://www.itmagination.com/open-jobs/ReactNativeDeveloper-8050000012886577) *、* [*Vue.js 开发人员*](https://www.itmagination.com/open-jobs/VuejsDeveloper-8050000013295265) *，还是 [*角形开发人员**，我们*](https://www.itmagination.com/open-jobs/SeniorFrontendEngineerwithAngular-8050000009516936)*

*原为发表于*[*https://www.itmagination.com*](https://www.itmagination.com/blog/5-reasons-why-startups-love-node-js)*。*