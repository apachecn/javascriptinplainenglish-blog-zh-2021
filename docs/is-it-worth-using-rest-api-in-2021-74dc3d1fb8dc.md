# 2021 年该不该用 REST API？

> 原文：<https://javascript.plainenglish.io/is-it-worth-using-rest-api-in-2021-74dc3d1fb8dc?source=collection_archive---------9----------------------->

## GraphQL 可能是一个更好的选择，但是你应该转换吗？

![](img/956ed6eb31f8653f3e1e5dece1176d73.png)

Photo by [bruce mars](https://unsplash.com/@brucemars?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

互联网先驱伊凡·苏泽兰说:“把我们认为很难的问题拿出来，然后找到一个简单的解决方案，这是非常令人满意的。最佳解决方案总是简单的。”

REST 或表征状态转移就是一个活生生的例子。

早在 20 世纪 90 年代，还没有统一的方法来标准化 web 设计选择和 API。

一个优雅而简单的解决方案是当务之急。

这正是在罗伊·菲尔丁领导下的一个专家小组得出的结论。我们称之为 REST APIs。

[菲尔丁总结了启发他构建 REST 的问题](https://en.wikipedia.org/wiki/Representational_state_transfer#:~:text=in%20a%20retrospective%20look%20at%20the%20development%20of%20rest%2C%20fielding%20said%3A):

> “我收到了来自 500 多名开发人员的评论，其中许多人都是拥有数十年经验的杰出工程师，我必须解释从最抽象的 Web 交互概念到 HTTP 语法的最细微的细节。
> 
> 这个过程将我的模型打磨成一套核心的原则、属性和约束，现在称之为 REST。"

但是就像世界上的一切一样，随着时间的推移，会有更好的替代品。

GraphQL 最近理所当然地获得了大量的流行，因为它给 REST 带来了很好的竞争。

GraphQL 的主要优势是它为客户提供了定义他们所需的数据结构的能力，并且来自服务器的响应也是以相同的结构定义的。

这可以防止服务器无缘无故地传输冗余数据。

然而，这不是另一个鼓励你盲目地从 REST 转向 GraphQL 的博客。

我将尝试解释 REST 的缺点，以及 GraphQL 如何克服这些缺点，如果这些缺点值得放弃，REST 将被讨论。

## 为什么即使在诞生 20 年后，REST 仍然如此受欢迎？

如上所述，REST 是由于缺乏构建 API 的统一和标准化过程而导致混乱的结果。

但那是在 2000 年。

二十多年后，人们仍然依赖 REST APIs，因为它提供了许多优势:

**#1。可伸缩性** : REST API 是可伸缩的。但这意味着什么呢？他们没有国籍。每个对 REST API 的调用都是一个独立的调用。

这使您能够缓存响应。REST 还允许您分离客户端和服务器端代码。使用 Redis 可以大大提高你的网站速度。

你可以在 Vue 中创建一个前端，并在后端使用 Django 开发的 REST APIs，这样会很好。

这种分离有助于管理代码库。

**#2。灵活性:** REST 允许开发人员根据自己的需要构造数据，并且客户知道预期的数据结构。

通过给予开发人员构建的自由，这些 API 可以处理各种形式的请求&从而以多种格式发送数据。因此，相同的 API 可以用于 web 和本地应用程序。

此外，这使您能够使用许多第三方 API，只需简单地查看它们的样本数据响应，最好的部分是您可能不必管理任何这些第三方 API。

[](/7-free-apis-that-nobody-is-talking-about-cf974e15917) [## 7 个没人谈论的免费 API

### 使用这些 API 创建独特而有趣的应用程序

javascript.plainenglish.io](/7-free-apis-that-nobody-is-talking-about-cf974e15917) 

## REST APIs 的缺点

如果 REST APIs 无可挑剔，GraphQL 的受欢迎程度就不会像今天这样。

在休息的情况下，它的一个优点也是它的缺点。

数据提取不足或过多是使用 REST 的核心缺点。

**由于 REST 给了开发者结构化数据的选择，因此它剥夺了客户定义他们需要的数据结构的自由*。***

*例如，假设您有一个网站和一个移动应用程序，两者共享同一个 API。*

*该 API 向网络和移动应用程序发送不同大小的单个图像的 URL。web 应用程序使用最大尺寸图像的 URL，而移动应用程序使用同样的方法，但使用较小尺寸的图像。*

*图像最小尺寸的 URL 不适合 web 应用程序，而移动应用程序则相反。*

*如果有一种方法可以准确地告诉 API 你…*

*这就是 GraphQL 发挥作用的地方。*

## *所以 GraphQL 比 REST 好？*

*答案不是简单的是或不是。*

*顾名思义，GraphQL 是一种查询语言，它让客户能够定义他们需要的数据结构，但它也有缺点。*

*我遇到的两个主要问题是缓存和缺乏速率限制。*

*让我们一个接一个地检查这两个:*

***缓存:**在 GraphQL 中进行缓存并非不可能，但是实现它并不像在 REST 中那样简单。*

*这是因为每个查询都可能是不同的，而 REST 的“查询”是相同的，我们确切地知道要缓存什么。*

*然而，大多数 GraphQL 库都提供了缓存机制。*

***速率限制:**同样，也不是不可能实现，但是速率限制不是 GraphQL 爱好者可以夸耀的事情。*

*最近，有许多 YouTube 视频和论坛在讨论限速 GraphQL，你可以看看这些。*

## *应该从 REST 切换到 GraphQL 还是相反？*

*两者都有各自的缺点和优点，这里没有通用的答案。*

*这完全取决于你的应用和个人偏好。*

*以下是您在选择这些 API 时应该考虑的几点:*

1.  *缓存:如果缓存是一个重要的方面，并且您经常需要它，那么 REST 是一个不错的选择。但是，如果只需要缓存站点的某些部分，可以使用 GraphQL 来实现这样的缓存机制。*
2.  *数据提取:REST 引入了数据提取不足/过量的问题。如果您计划在多种设备上使用相同的 API，并且希望能够自由地允许客户端结构化数据，那么毫无疑问，GraphQL 是您的不二之选。*
3.  *解耦:每当前端需要新数据时，比如显示全名而不仅仅是名字，他们可以简单地改变查询，而不改变后端的任何内容。它帮助后端和前端团队独立工作。*
4.  *简单:如果你是初学者，那么我建议你至少学习 REST，因为它打开了一扇机会之门。此外，如果您正在构建一个看不到可伸缩性的辅助项目，或者仅仅是一个辅助项目，那么 REST 是首选，因为它易于实现(当然，除非您的辅助项目特别需要 GraphQL 的能力)。*

## *最后的想法*

*作为一名 web 开发人员，看到像 REST 和 GraphQL 这样的选项给我带来了快乐，但同时，它也造成了错误规划大型项目和重写后端代码的恐惧。*

*GraphQL 和 REST 各有利弊，事先了解它们可以让你省去无数的编码和纠正错误的时间。*

> *选择这两者中的任何一个都取决于您的应用需求。*

*它们都不完美，但是如果你在使用它们之前三思，它们会是你下一个应用的完美选择。*

*感谢阅读！*

**更多内容尽在*[*plain English . io*](http://plainenglish.io/)*