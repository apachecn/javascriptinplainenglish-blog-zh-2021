# 依赖地狱:开发 Web 应用时最糟糕的场景

> 原文：<https://javascript.plainenglish.io/dependency-hell-the-worst-possible-scenario-while-developing-apps-750b37405d20?source=collection_archive---------9----------------------->

## 利用社区创建的包可能非常有用并且节省时间，但是有一些问题你应该知道。

![](img/2cc3adf2f68863bfa04df24f307e350a.png)

Photo by [Ralph (Ravi) Kayden](https://unsplash.com/@ralphkayden?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/s/photos/connection?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

从一开始到现在，我作为一名 web 开发人员经历了几个阶段。积累了 7 年的经验，我认为这些阶段对于每个新的 web 开发人员来说都是非常相似的。

在第一阶段，我刚刚开始学习 JavaScript，还有很多东西需要学习。我用一个普通的`index.html`开始了一个计算器项目，并通过添加一个`main.css`增加了一些趣味。为了做一些基本的计算，我使用了 JavaScript 和一些 DOM 方法。除了我之外，没有任何人写过代码。一切都很难理解，但同时又很简单。

在第二阶段，我遇到了库:一些慈善人士编写的代码，帮助我们简化开发过程。例如，最终没有必要编写一个函数来将两个数字相加。多方便啊！我只是添加了一个`script`标签，一堆功能就可以使用了。另外，在这个阶段，我遇到了`npm`之类的 CLI 工具，我尽量避开了。因为它们令人困惑，我认为没有必要。我可以手动做任何事情。我可以创建文件，我可以找到 CDN 链接并将它们添加到我的 HTML 中。

第三阶段是我决定给 CLI 工具一个机会并爱上它们的阶段。因为他们为我做了一切。我可以用 Vite 或 CRA 为 React 应用程序创建一个普通的 JS 项目。我不必手动做所有的事情。此外，我和图书馆的关系越来越好。我需要什么吗？我去了 NPM 网站，找到了一个适合我的。其余部分是通过 npm CLI 完成的。我可以添加任意多的库。

依赖关系的问题就从这里开始了。外包是现代发展不可或缺的一部分。因为我们必须消除棘手的部分，专注于开发应用程序。然而，有一些合理的观点可以避免给你的应用程序增加一个依赖项。

# 有时候，使用包可能有些过头了

![](img/35cf26a8d01288be27060d27e6b5f69b.png)

Photo by [Markus Spiske](https://unsplash.com/@markusspiske?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

JavaScript 社区是巨大的！我可以保证你可以只用 NPM 上的包来构建一个应用程序，而不用写一行逻辑代码。因为每天都有成千上万新的有用的库被开发者发布和使用。甚至有一个库来检查一个数字是否与超过 20 万周下载量持平。

为了看看一个简单的包是否可以有很多下载，我创建了一个包，它将里面的内容固定在一定数量的行上。我所做的只是写了 3 行 CSS 并用 JavaScript 应用了一个类。就是这样！任何人都可以在 2 分钟内完成这项工作，但该软件包在第一天就被安装了 200 多次。这是非常可悲的，因为开发人员开始变得懒惰，并开始为所有东西搜索一个库。然而，JavaScript 是一种强大的语言，在 90%的情况下，经过大量的思考，我相信你可以找到一种方法来处理这个问题，而不会给应用程序增加更多的依赖。

让我们假设我想在我的网站上有一个很酷的翻转动画。有两条路可走。第一个是下载一个翻转动画库并立即解决问题，或者我可以阅读[这篇](https://css-tricks.com/animating-layouts-with-the-flip-technique/) CSS 技巧文章并实现我自己的逻辑来实现这一点。第一个很简单，但是虽然你可以自己做，并且最终感觉很成功，为什么你要增加一个依赖项，走容易的路呢？

# JavaScript 越少，Web 应用越快

这有点讽刺，但作为一名 JavaScript 开发人员，我的目的是尽可能少地为客户端提供 JavaScript，因为 JavaScript 的数量越多，加载和执行时间就越长，从而导致糟糕的用户体验和落后的网站。但是这些依赖是如何对我的应用程序产生负面影响的呢？它们都有用途，没有一个是闲置的。这个论点的要点是:依赖关系中有未使用的部分。

当一个依赖项被添加到一个应用程序中时，实际上所有的依赖项都被下载到客户端，即使有一些部分你不使用。通常，一个库有许多方法来处理所有的极端情况。例如，让我们看看*验证器*库。这是一个处理从手机号码到电子邮件的各种验证的库。它非常有用，每周都有数百万开发者使用。使用这个库，我们可以验证输入并检查其值是否是电子邮件，如下所示:

![](img/ff2d2162dcd8ec20f83f5bf79e457d4e.png)

一切都很简单。我导入了这个库，并使用它附带的`isEmail`方法来验证输入。但是这里有一个有趣的事实:有 91 种方法来自于 *Validator* 库，而我只用了一种。如果我没有专门配置的构建工具，这些未使用的代码块将被发送到客户端并增加加载时间。但是如果我使用纯 JavaScript 并借助 Stack Overflow，我可以使用 RegExp 创建我的自定义函数来验证输入。这样做，我只得到我用的那部分，对应用的性能有贡献。

# 一些软件包可能未经优化，并且包含漏洞

另一个阻止我在应用程序上添加另一个依赖的问题是，并不是每个库都是由经验丰富的专业程序员编写的，他们会检查代码的漏洞和优化。NPM 是一个开放的平台，任何人都可以创建一个社区使用的图书馆。因此，有许多库使我的应用程序不那么优化，更容易被利用。此外，如果不安装和测试一个包，就无法检查它的漏洞。所以，如果没有必要的话，添加另一个库是一种赌博，要么有不好的结果，要么有好的结果。我认为在你可以创建没有漏洞的相同功能时冒这个风险是愚蠢的举动，应该避免。

# 结论

这些是在给你的应用程序增加一个依赖时要三思的主要原因。当我开发应用程序时，我尽可能减少依赖，因为我知道如果我写代码而不是安装一个库，我只是根据我的需要来定制它，仅此而已。因此，编写的代码最适合应用程序的上下文，不会产生任何进一步的问题。

所以，要意识到手中 JavaScript 的强大，不要害怕使用它。

伙计们，这个故事到此为止。希望你觉得有用。喜欢的话，一定要鼓掌。敬请期待下一个故事！

*更多内容尽在*[*plain English . io*](http://plainenglish.io/)