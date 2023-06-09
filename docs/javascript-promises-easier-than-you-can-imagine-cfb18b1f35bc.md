# JavaScript 承诺比你想象的要容易

> 原文：<https://javascript.plainenglish.io/javascript-promises-easier-than-you-can-imagine-cfb18b1f35bc?source=collection_archive---------7----------------------->

![](img/7c82c6e8e51df9d57c8208d232d0e7de.png)

当我在编程中遇到一个新的抽象概念时，我总是试图把它和一些简单易懂的东西联系起来，比如食物😋我喜欢食物！我见过的几乎每个人都这样。这就是为什么今天我们要把 JavaScript 中的承诺和异步代码执行看作美味的食物。我在 RBK 大学和我的学生一起尝试过，效果非常好。这就是为什么我要将异步代码执行与从餐馆订餐联系起来。现在，让我们继续订购一些承诺。

# **承诺和食物**

午餐时间到了，你饿了。你不会做饭，甚至没有时间做饭。这就是为什么你决定去街角的麦当劳餐厅吃午餐。你一直喜欢他们做的芝士汉堡，所以你的决定一点也不难。

你去收银台向他要一个芝士汉堡。你付了餐费，作为回报，他给了你一张票。现在，这张票就是 JavaScript 承诺。不是食物，不是价值，而是未来的价值。收银员(或服务员)给你一个承诺，他会把你的饭送回来。什么时候？它可能需要几秒或几分钟，就像它可能需要一个小时一样。这完全取决于做饭的速度有多快，以及有多少人已经在排队了。在最糟糕的情况下，服务员会走过来告诉你他们没有奶酪了😫也许你可以点别的。

承诺也是如此，你执行一些异步代码(比如从客户端向服务器发送请求)，然后等待你的响应。同时，作为回报，您将获得对未来数据的承诺。

当汉堡(或数据)最终准备好时，你可以**然后**开始吃它，享受它的味道。否则，你可以点别的或者去另一家还有奶酪的餐馆。

承诺也是如此。如果您得到了您的响应，您就可以操作该数据或将其输出给用户。另一方面，如果你不这样做，你会做其他事情，比如通知用户没有数据了。

# 使用承诺向 API 发送请求

现在，让我们看一个代码示例。对于这个博客，我将向 [**Github API**](https://docs.github.com/en/rest) 发送一个 GET 请求。然而，API 并不发回食物。然而，Github API 可以给我们发回另一个比食物更好的东西！是的，你猜对了… [**表情符号**](https://docs.github.com/en/rest/reference/emojis) 🎉 🎉我们开始吧！

第一件事当然是创建一个 JavaScript 文件。我准备把它命名为“index.js”。然后，我们需要一个来自 Github 的 API 令牌来发送请求。你可以在[https://github.com/settings/tokens](https://github.com/settings/tokens)上生成你自己的。

我将把我自己的密钥放在一个单独的文件中，然后将其导入 index.js，我将使用 npm 来安装 Axios。

我导入了 [Axios](https://github.com/axios/axios) 来使用它向 API 发送 http 请求。这是一个出色的基于 promise 的 HTTP 客户端库。在这篇博客中，我不打算深入研究如何使用[本机承诺](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)或外部库如[蓝鸟](https://www.npmjs.com/package/bluebird)来创建并使函数返回承诺。相反，我将关注如何发送请求，并以基于承诺的模式处理返回值。

有了这些，现在让我们点一些食物(一些表情符号)😅

为此，我创建了一个名为 **getEmojis** 的函数，并在第 21 行调用它。如果我们深入函数定义，我们会发现在第 5 行，我们使用 get 方法用 Axios 发出 get 请求。该方法有两个参数:路径*“https://API . github . com/e mojis”和一个包含 *headers* 属性的对象，其中我们将导入的 API_TOKEN 作为值提供给*授权。**

这个调用现在没有立即返回值(因为我们没有立即得到我们的芝士汉堡)。相反，它返回对未来值的承诺。毕竟，从远程服务器获得响应需要时间，就像厨师需要时间准备汉堡一样。

Promise 类型的返回值有两个不同的重要方法:**。然后是()**和 **catch()** 。第一个将在请求成功时被调用(返回承诺值)，而第二个将在请求失败时被调用(没有返回承诺值)。现在，请求可能因为许多原因而失败，包括但不限于失去网络访问或者我们将它发送到了一个不存在的路径(比如“https://api.github.com/food ”,因为 Github API 到目前为止不提供食物)。

因此，API 说，当我们在那个**端点**上发送一个 **GET** 请求时，它将向我们发回 GitHub 处理的表情符号的完整列表。这就是为什么我假设我的回调函数，将会被执行，将会有一个参数，就是表情符号的数组。对于本例，我将只把它们记录到控制台。在另一个上下文中，当您的汉堡准备好并端上桌时，您将执行带有参数*(汉堡)的函数 *eatBurger* 。*

如果请求失败，我将*捕捉*返回给我的错误消息并抛出，以便能够调试我的代码。

# *结论*

承诺是 JavaScript 的一大亮点。他们允许我们有一个非常可读的代码，并把我们从回调地狱中拯救出来，在回调地狱中，你在一个回调中执行另一个回调。事实上，在回调中，我们的代码变得越来越水平，而在承诺中，它变得垂直有序，这使得它对于开发人员和普通人来说是可读的。

我们得到的承诺值有两个主要方法。成功时执行的 then()，以及。失败时执行的 catch()。