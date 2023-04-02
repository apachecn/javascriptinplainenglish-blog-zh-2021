# 学习使用节点核心 API 创建“获取”API

> 原文：<https://javascript.plainenglish.io/learn-to-create-a-fetch-api-with-the-node-core-api-91c1e9119cba?source=collection_archive---------16----------------------->

![](img/365113e27f170553896e0301234fcbd4.png)

Photo by [David Rangel](https://unsplash.com/@rangel?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

对于我写的每一篇文章，我的目标是为阅读这篇文章的人传递正确的思维框架，这样他们可以在离开现场时对所介绍的概念有更深的理解。

从广义上讲，写作或教学的目的是让学习者更加好奇，并为他们提供一些解决问题的过程，他们可以在其他开放式或远程类似的问题中进行归纳。

## 问题描述:

今天，我想解决的问题是:

**“如何使用 async/await 在 Node.js 中的 http 模块之上构建抽象”**

基本上，“http”模块遵循回调模式。因此，我们可能会也可能不会将它完全转换成“异步/等待”模式。

**注意:**如果在 Node.js 代码中使用 commonJS，请替换`import ... frpm "..." with const ... = require("...")`。

http 请求的一般格式如下:

因此，正如我们所看到的，可能没有空间将其格式更改为基于承诺的功能。

## 解决问题的过程:

第一部分:

我们想要完成的第一个目标是在我们的解决方案中使用 ***async/await*** 技术。首先，我们需要知道`**async/await**`是建立在承诺之上的模式。因此，基于承诺的概念，我们要编写的模块必须返回一个承诺。

因此该模块的一般格式如下:

因此，我们现在已经创建了一个函数，我们希望它作为核心“http”模块的包装器或父函数。

第二部分:

我们现在问我们需要哪些核心模块来使我们的新模块工作。根据我们的观察，我们已经看到了以“http”或“https”开头的网站和资源。

因此，我们需要一种方法来指定我们的模块是通用的，以便它可以处理“http”和“https”模块。

**练习:**尝试添加“fetch”函数的逻辑来处理 http 和 https 协议

现在我们已经形成了函数的基本结构，现在我们想在`fetch`函数体中使用`http`和`https`模块。

第三部分:

我们有协议变量，它可以是对 http 或 https 模块的引用。让我们将它添加到 fetch 函数体中

因此，基于我们传递给 fetch 函数的 url，我们可以使用 http 或 https 功能之一发送请求，所以让我们将 url 作为 protocol.get 参数传递:

第四部分:

不幸的是，http/https 模块不能在 Node.js 中转换为 promises，所以我们要解决的问题是在协议内部使用回调，这样最后我们就有了一个基于 promise 的 fetch 模块。

首先，让我们解决 protocol.get(url)，我们应该首先创建回调的必要功能。

我们应该知道一些关于 Node.js 在发出请求后如何接收数据的概念:

*   Node.js 以块的形式接收数据，即接收到的小信息包，然后在我们的服务器逻辑中打包在一起。
*   这些块在 Node.js 中以`Buffer`的形式被接收。因此，我们可能必须在代码中将它们转换成有意义的格式。
*   接收块的过程是一个异步操作，所以我们需要确保块是按顺序接收的，这样我们的服务器逻辑中就会有一个有组织的块集合

因此，我们要解决的问题是，我们如何按照发送到服务器的顺序获取数据块。

换句话说，我们必须等待每个数据块被完全正确地接收，然后才能接受下一个即将到来的数据块。

记住，我们正试图使用`async/await`特性来解决这个问题，所以如果我们搜索或了解**迭代器**，一个`await for ...of`可能是一个可靠的选择。

```
for await (const chunk of res) { ... }
```

所以现在我们应该问:

"在我们确保它们以正确的顺序被接收之后，我们如何收集这些块？"。

想想在 JavaScript 和 Node.js 中存储本质上相似的值的情况，您可以得出结论，将块放在一个数组中是一个好的决定。

以下是 body 数组内容的示例:

```
[
  <Buffer 7b 22 70 61 67 65 22 3a 32 2c 22 70 65 72 5f 70 61 67 65 22 3a 36 2c 22 74 6f 74 61 6c 22 3a 31 32 2c 22 74 6f 74 61 6c 5f 70 61 67 65 73 22 3a 32 2c ... 428 more bytes>,
  <Buffer 64 22 3a 31 30 2c 22 65 6d 61 69 6c 22 3a 22 62 79 72 6f 6e 2e 66 69 65 6c 64 73 40 72 65 71 72 65 73 2e 69 6e 22 2c 22 66 69 72 73 74 5f 6e 61 6d 65 ... 502 more bytes>
]
```

从现在开始，我们可以采取两种方法，要么在一个地方编写整个回调函数，要么让回调函数由小函数组成。我认为养成编写小函数的习惯是一项长期受益的技能，所以让我们遵循第二种方法。

让我们创建一个名为`collectChunks`的函数:

*   它应该接受响应对象
*   它应该按顺序收集数据块
*   它应该返回块的集合以供进一步处理

**练习)**编写`collectChunks`函数，使其满足上述条件:

如果我们测试下面的函数，我们会得到下面的错误:

```
for await (const chunk of res) {
      ^^^^^

SyntaxError: Unexpected reserved word
```

一个错误等于一个学习的机会。因为我们已经在函数体中使用了`await`关键字，所以我们需要使函数充当异步函数，以便使其正确工作。所以`collectChunks`的最终实现如下:

到目前为止，fetch fetch 函数的一般结构如下:

下一个任务是编写这个 someCallback，它调用内部的 collectChunks 函数。

这个回调函数的正确名称应该是`getData`。这一职能应该:

1.  调用内部的 collectChunks 从外部源获取数据
2.  它应该将收集的缓冲区转换成代码其他部分可读的格式

**练习)**根据上述要求编写 getData

现在让我们一起编写它，因为 collectChunks 被声明为一个`async`函数，它将返回一个承诺，所以为了在 getData 函数中使用它，我们必须将 getData 也声明为一个`async`函数:

**练习)**你可以去掉 async/await 关键字，看看会发生什么，加深你对它们如何工作的理解。

现在 chunks 变量包含了一个缓冲区数组。我们必须将数组转换成可读的格式，对吗？

如果您在互联网上搜索缓冲区对象，您会发现它们有一个`toString()`方法，使用 UTF8 编码将缓冲区转换为字符串。因此，一个可能的解决方案是:

```
chunks.map((buffer) => buffer.toString())
```

但是我们必须再次把所有的块放在一起，然后再次解析它们，所以也许我们可以把所有的块放在一起，然后在一个地方解析它们。

这听起来像是我们的 getData 函数的额外工作，它的工作只是获取数据而不是处理接收到的数据。您猜对了，我们有一个创建新功能的环境，它应该:

*   连接所有缓冲器
*   解析它们以备后用
*   返回解析的数据

**练习)**试编写这个名为`parseData`的函数来做上述要求:

所以 getData 函数变成了:

如果没有适当的错误处理工具，任何处理承诺的函数都是不完整的，异步/等待函数中的错误处理惯例是使用 **try/catch 块**。

让我们使用 try/catch 块修改 getData 函数。

修改后，我们的代码如下:

现在是时候检查 fetch 函数是否按预期工作了:

**练习)**在 getData 函数的 try 块中放置一个`console.log(data)`，并使用 fetch 测试一个免费的 API，示例如下:

```
fetch('https://reqres.in/api/users?page=2');
```

控制台上打印的结果将是:

我们可能想把它写到一个文件中，或者保存到一个数据库中，或者对数据做一些逻辑处理。

但是等等！目光敏锐的学习者可能会问:

"在 getData 函数中处理数据是否是某种反模式？"

她是对的，如果我们决定遵循单一责任原则，我们的职能应该做一件事，那就是获取数据，不多也不少。

猜猜看，我们有一个新问题要解决:

## 问题陈述:

我们希望 fetch 模块独立于其他函数或额外的工作。

事实上，我们已经声明了我们的`fetch`函数，以便它返回一个承诺，我们以后可以在代码的其他部分使用它。

要测试当前条件，请记录 fetch 函数返回的值:

因此，我们的第一个想法是，测试现在已经开始，我们可以这样做:

```
test.then(() => console.log('fetch works perfectly'));
```

如果运行该模块，您会看到消息不会打印在控制台上。这是我们需要检查我们对承诺的理解的地方。

只需检查我们到目前为止编写的 fetch 函数

您可能会注意到，除了两个空闲参数: **resolve 和 reject** ，每个人都在忙碌和工作。

我亲爱的华生，正如夏洛克·福尔摩斯所说，“我们可能已经找到了罪犯！”。

在继续之前，试着解释什么是承诺以及承诺是如何运作的。

基于承诺定义:

*Promise 将两个函数作为其参数，并根据 Promise 的状态调用每个函数。如果承诺状态被满足，将调用 resolve 函数，如果其状态被拒绝，将调用 reject 函数。*

那么，我们如何使用这两个函数，以便以后可以访问 fetch 函数的结果呢？

通过仔细观察 fetch 函数的主体，我们可以看到只有一个函数能够接受 resolve 和 reject 作为它的参数，那就是:`getData`

你可能认为问题已经解决了，就像这样:

试着运行这个模块，看看会发生什么。您会得到以下错误:

```
UnhandledPromiseRejectionWarning: ReferenceError: res is not defined
```

你有权问为什么会发生这种情况。

原因是对于 protocol.get()，您应该像我们在第一个位置对“getData”功能所做的那样传递一个函数或一个函数的引用，但是现在我们将 getData()作为一个参数调用。

那么在其他类似的问题中，你会如何解决这样的问题呢？

是的，首先定义问题:

*   您需要向 protocol.get()传递一个函数
*   您还需要将 resolve 和 reject 传递给 getData 函数

请记住，传递给 protocol.get()的函数的形式是:

```
(req,res) => { ... }
```

此外，还需要将 res 对象传递给 getData 以及 resolve 和 reject:

```
getData(res, resolve, reject)
```

因此我们可以得出结论，getData 必须在传递给 protocol.get()的匿名函数内部调用，如下所示:

```
protocol.get(url, (res) => getData(res, resolve, reject));
```

现在，我们可以在 getData 函数的范围内访问 resolve and reject 函数，我们可以修改它来处理它使用 resolve 函数接收的数据:

所以我们现在已经编写了 fetch 函数，我们希望它返回一个承诺，即 **thenable** 。让我们检查一下我们的期望:

最后，我们设法创建了一个基于 promised 的 http 模块。

最终代码:

现在，您可以在另一个模块中导入`fetch`,并将其用于其他目的:

**练习)**创建一个`getUsers.js`文件并测试以下内容:

# 结论:

*   解决任何问题都是一个多步骤、迭代的过程。不要期望在了解问题各个方面的情况下一次性解决问题。
*   我希望你能理解我们在这里所经历的过程，并对你面临的其他问题采用同样的方法。
*   每当你记录一条数据并收到与你预期不同的东西时，这是一个很好的机会来重新检查你的知识和理解，并在更深的层次上学习这些概念。

*更多内容看*[***plain English . io***](http://plainenglish.io/)