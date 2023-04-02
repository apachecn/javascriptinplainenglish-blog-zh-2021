# 2021 年的动态网络

> 原文：<https://javascript.plainenglish.io/the-dynamic-web-ee3c89a14225?source=collection_archive---------15----------------------->

## 让我们来探索驱动现代网站的东西

![](img/03e2a1d566f7612ccc08361dad0aa271.png)

Image By [Geralt](https://pixabay.com/users/geralt-9301/)

在我之前的帖子中，我向你介绍了网站如何工作的基础知识。但那只是静态的 T4 形式的网站。在本帖中，我们将了解“静态”的实际含义，以及现代 web 开发中使用的其他重要概念。你也会得到我在上一篇文章中留给你的那个问题的答案。😎

我们之前了解到，网站是网页的集合，网页只是普通的 HTML 文件。当我们访问一个网站时，我们会收到一个呈现在浏览器中的 HTML 文件。这些是*静态页面；*意味着每次都向客户提供相同的页面。这些页面以完整的形式呈现在服务器上。无论从客户端收到什么请求，它们都不会改变。但这并不总是可取的。

# 服务器端渲染

假设我有一个页面，要求您在表单中输入您的姓名。在您提交表单后，我想在页面上显示您的名字和一条消息，例如-“Hello<your-name>”。如果您还记得上一篇文章，当提交任何表单时，我们(大部分)都会向服务器发出一个`POST`请求。服务器应该对提交的数据(你的名字)做一些事情，并向你发送一个包含更新信息的新页面。</your-name>

我们不能对静态页面这样做，因为每次我们提交不同的名称时，新页面应该是不同的。我们在服务器上没有完全预编码的页面，因为要呈现的数据不是静态的。这就是为什么我们需要**在每次收到请求时在服务器上呈现/生成我们的页面以及必要的数据**，然后将其发送给客户端。这被称为**服务器端渲染**，其中页面是动态的*。这里有一个动态页面的[实例，如果你想结帐，你必须提交一个 API 端点来接收一些响应(或者输入任何内容来接收错误响应)。](https://apipaginator.herokuapp.com)*

*这个概念非常简单——只要有些数据没有预先定义，我们就使用*模板*值作为占位符；等到收到请求和数据时，在将数据发送给客户端之前，将数据注入页面。有像 [EJS](https://ejs.co) 和 [Pug](https://pugjs.org/) 这样的[模板引擎](https://www.pabbly.com/tutorials/template-engine-in-expressjs/)可以简化我们通过模板页面生成 HTML 的工作。*

## *SSR 的缺点*

*SSR 有两个主要限制，如下所列-*

*   ***慢速导航**——你知道当我们导航通过不同的路线( **/home** 到 **/about-me** )时，浏览器向服务器发出新的`GET`请求，要求关联页面。这使得导航非常慢，因为每次页面转换都要启动一个全新的请求。静态和服务器端呈现的页面都会发生这种情况。*
*   ***高服务器负载** —因为每个请求所需的页面都在服务器上呈现，所以服务器上的负载随着显著的流量而增加；导致高[延迟率](https://en.wikipedia.org/wiki/Latency_(engineering))。*

*但是等一下…如果我们可以在服务器端生成页面，为什么不尝试在客户端做呢？🤔对，遇见 CSR！*

# *客户端渲染*

*如果你注意到，当你从一条路线导航到另一条路线时，这个网站并不刷新，页面立即加载；这意味着一旦网站最初加载*时*，它不会向服务器请求任何其他页面。这被称为**客户端渲染**。*

*在这种技术中，客户机只接收一个 HTML 文件，以及一堆 JavaScript 代码。基于所请求的页面/路由，该页面的内容通过 JavaScript 注入到 HTML 中。因此，如果您稍后导航到不同的路径，只有必要的*页面内容会被重新呈现。不需要向服务器发出请求，所有的路由工作都在客户端处理，这使得导航速度非常快！🚀**

*使用这种方法的网站被归类为[单页面应用](https://en.wikipedia.org/wiki/Single-page_application)。
但我们不必对这种方法太满意，因为它也有自己的缺点。*

## *企业社会责任的缺点*

*   *糟糕的搜索排名——因为客户端最初收到的只是一个空白页面，页面上没有什么可看的。因此，搜索引擎不知道我们的内容。尽管谷歌声称他们确实抓取了使用 JavaScript 生成的页面，但这些网站的搜索排名可能真的很差。*
*   ***初始加载缓慢**——因为 HTML 附带了大量的 JavaScript 代码，初始加载时间显著增加。此外，当由浏览器生成页面时，页面的交互时间也会增加。*
*   ***JavaScript 强制** —出于安全原因，许多用户在浏览器设置中禁用 JavaScript。但是这也阻止了 JavaScript 生成页面内容，因此，他们的浏览器只能呈现一个空白页面。🥴*

*现在，你猜对了；我们有另一种方法来接管！🥳*

# *预渲染*

*这种方法是静态和客户端渲染站点的简单混合。在我们继续之前，让我们先回忆一下几点-*

1.  *在最简单的方法中，即静态站点，我们在服务器上手动编码 HTML 页面。当接收到对其中一个页面的请求时，服务该页面。*
2.  *在服务器端渲染中，我们有模板页面。当客户端请求某个页面时，我们首先通过将接收到的数据注入到页面内容中来在服务器上呈现它；然后发送给客户端。*
3.  *但是在客户端渲染中，我们只提供一个模板页面。所有的路由和页面渲染都在客户端处理。*

*现在来看预渲染或者说*静态站点生成*，开发过程类似于 CSR。唯一的区别是**我们在服务器**上预渲染/预生成所有的静态页面。这是在[构建/编译时间](https://en.wikipedia.org/wiki/Compile_time)完成的。所以我们在服务器上预先渲染了整个网站。*

*除非它到达客户端，否则它的行为就像一个静态站点，根据请求提供某个页面。现在为了理解客户端发生了什么，你应该首先了解术语**水合**。*

> *[*水合*](https://en.wikipedia.org/wiki/Hydration_(web_development)) *或再水合是一种技术，其中客户端 JavaScript 通过将事件处理程序附加到 HTML 元素来将静态 HTML 网页转换为动态网页。
> —维基百科**

*一旦静态页面呈现在浏览器中，剩下的唯一工作就是将它再次转换成动态 SPA 页面，以便所有进一步的导航事件都在客户端处理。所以我们*通过附加事件处理程序来水合*页面。这真的很强大，因为它从静态站点和 CSR 方法中获益，以消除/最小化它们的缺点。*

*但是预渲染有两个巨大的限制-*

*   ***不适合非常大的网站** —这种限制的原因是因为所有的页面都是在服务器端预先构建的，构建时间会随着页面数量的增加而增加。基于服务器资源，对于这种方法来说，几百个页面就足够了。*
*   ***对于过于频繁变化的内容效率低下** —除了大量的构建时间之外，这些网站的每一个变化，即使是很小的变化，都需要重新构建/重新编译整个网站！这会消耗更多的时间和资源。因此，这种方法不适合内容变化过于频繁的网站。*

*所以，这就是动态网站所采用的方法。每种方法的使用取决于网站的规模和要求，因此，在选择任何一种方法之前，应该进行彻底的比较。*

*现在让我来解释一下🧙在现代网站中使用的其他一些重要概念。*

# *结构*

*我们都知道，人类的本性迫使他们将简单的东西组合成疯狂的东西；然后用这些疯狂的东西制造更疯狂的东西，如此循环。这就是我们今天看到的周围事物的由来。*库*也是如此。*

*每个编程社区都有大量的头脑，他们为了社区的利益，一起工作来创建可重用的、挽救生命的库。在 Node.js 世界中，这些可互换地被称为*包*，因为它们由像 [NPM](https://npmjs.com/) 和 [Yarn](https://yarnpkg.com/) 这样的包管理器托管。*

*框架使用多个库将游戏带到下一个级别。**框架是一个额外的抽象层，以某种方式使构建应用程序变得更加容易**。例如，[我的博客](https://blog.sapinder.dev)是用 [Gatsby.js](https://gatsby.dev/) 框架构建的，而不是普通的 JavaScript，它遵循了 SSG 的方法。然后还有 Next.js、Angular、Vue、Svelte，以及许多其他遵循这种或那种方法的框架。*

*除非你习惯于用普通的 JavaScript 构建网站，否则你不需要急着使用这些框架，因为在进入抽象层之前，基本的理解是很重要的。框架在当今世界有自己的位置，但是它们不是强制性的。现在，让我们开始这篇文章的最后一部分吧！*

# *渐进式网络应用*

*关于这个话题，我没什么可说的，除了“他们试图让网站像手机上的本地应用一样”。尝试在您的浏览器中访问 twitter.com；关闭选项卡；断开与 internet 的连接；再次访问网站；然后嘣💥，web 应用程序在没有互联网连接的情况下加载！Twitter.com 是一个进步的网络应用的例子。*

*[渐进式网络应用](https://developers.google.com/web/updates/2015/12/getting-started-pwa)专注于像这样的事情*

*   *缓存页面以实现脱机可用性。*
*   *缓存其他资源，如图像等。，以便更快地从服务器加载。*
*   *通过提供必要的网站信息来处理诸如“添加到主屏幕”之类的事情。*
*   *利用 API，如推送通知等。*

*PWAs 现在越来越受欢迎，因为它们为网站提供了类似应用程序的体验；因此，名副其实的标题**“网络应用”**。*

# *包扎*

*所以这就是我想在这篇文章中包含的全部内容。如果你喜欢我的写作风格，你可以关注我，永远不要错过我未来的任何帖子。你也可以在 [Twitter](https://twitter.com/sapinder_dev) 、 [Github](https://github.com/sapinder-pal) 和 [LinkedIn](https://www.linkedin.com/in/sapinder-singh/) 上查看我的信息。*

***平安！** ✌️*

**更多内容请看*[***plain English . io***](http://plainenglish.io)*