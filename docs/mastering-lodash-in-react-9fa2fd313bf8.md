# 掌握反应中的碘

> 原文：<https://javascript.plainenglish.io/mastering-lodash-in-react-9fa2fd313bf8?source=collection_archive---------6----------------------->

## 使用实用程序库使您的 React 项目更好

![](img/b469b9c09b7c81c648f319902196cebb.png)

Created by Author

作为懒惰的开发人员，我们通常倾向于使用外部资源来解决我们的问题。说到解决问题，实用程序库解决了很多问题。最受欢迎的实用程序库之一是 [lodash](https://lodash.com/) 。

> Lodash 是一个 JavaScript 实用程序库。它提供了各种操作数组、对象、字符串和数字的函数。

由于 Lodash 是用 Javascript 编写的，所以我们可以在任何 React 应用程序中使用它。在 React 应用程序中使用 Lodash 是一个简单明了的过程。

**要在 React 中开始使用 Lodash，您需要:**

*   运行`npm install lodash`安装 Lodash
*   通过编写`import _ from lodash`将 Lodash 导入您的项目

Lodash 有助于简化您的代码，并使您的应用程序运行得更快。它通过承担一些通常你必须自己做的工作来做到这一点。🦥

> Lodash 有助于处理那些你不想一遍又一遍做的小事，比如从对象中添加或删除属性，或者从列表中添加或删除元素。

# 反应堆里的碘用来做什么

**Lodash 围绕四个主要理念构建:**

1.  高雅
2.  简单
3.  一致性
4.  表演

> 如果您希望您的代码库具有这些品质，您应该考虑将 Lodash 添加到 React 项目中。

Lodash 提供函数式编程助手，不扩展任何内置对象。它包含了常用的函数助手，比如将函数应用到数组的每个元素的`map`，而不会弄乱全局名称空间。

它还有 JSON 迭代器，对于处理来自 API 端点的数据非常有用。

> 这个库在 React 项目中被广泛使用，因为它提供了一种在 React 组件中处理集合和数组的简单方法。在下面的例子中，我们将展示一些可以使用 Lodash 解决的问题。

假设我们有一个用户可以输入任何内容的输入框。当用户输入和输入改变时，我们希望同时对给定的关键字进行搜索。

然而，我们不希望每次用户按下按钮时都执行搜索。这将导致大量的 API 请求和缓慢的性能。

幸运的是，这个问题可以通过使用`debounce`来解决。

Input.jsx

假设我们有一个包含任意值的数组。但是我们只想显示唯一的值。我们可以使用 Lodash 中的函数，而不是编写一个只查找唯一值的函数。

Users.jsx

# 在 React 中使用 Lodash

在上一节中，我们仔细研究了 Lodash，以及如何使用它来解决 React 应用程序中的常见问题。但是我们没有完全讨论它的用法。🦧

> 如果您在 React 项目中使用 Lodash，您需要知道如何正确使用它。

正如我们之前指出的，Lodash 库包含了许多帮助函数。这使得图书馆的规模非常大。但是在你的 React 项目中，你使用它们的机会真的很小。

> 在实际项目中，我们通常只导入四五个函数。

即使您只导入和使用一个 Lodash 函数，您的项目也会下载整个 Lodash 库。这将导致您的 React 应用程序在最终大小上增长，最终会变得更慢。特别是对于网络连接不好的用户。

幸运的是，这个问题可以通过下面的方法解决。

当我们将 Lodash 下载到我们的项目中时，它会下载它包含的所有实用函数。然而，这部分并没有使我们的应用程序变得更大。问题是当我们在任何文件中写`import _ from lodash`时。

通过编写给定的 import 语句，我们告诉大家我们想要使用整个 Lodash 库。而实际上，我们只想使用一个特定的函数。

为了只导入一个特定的函数，我们可以按照下面的方式编写我们的 import 语句。

```
import map from "lodash/map"
import forEach from "lodash/forEach"
```

这将阻止在我们的最终网站中包含整个 Lodash 库。但是，它将只包含我们指定的函数。

本文开头。我们向您展示了将 Lodash 添加到 React 项目中的方法。是靠跑`npm install lodash`的。

该命令将下载整个 Lodash 库并将其添加到您的项目中。然而，还有一种方法可以只下载库的特定部分。

> 每个 Lodash 函数都有自己的存储库，可以单独安装。

假设我们只需要使用`map`功能。我们可以通过运行`npm install lodash.map`来安装。然后简单地导入它。

```
import map from "lodash.map"
```

这种方法的好处是它的性能。因为只下载一个函数比下载数百个函数要快得多。问题是当我们需要使用多个功能时，我们必须分别安装它们。

# Lodash 替代品

Lodash 是一个很棒的实用程序库，但它不是唯一的。有许多项目都专注于实用功能。在这一部分，我们将列出其中的一些。💡

> 这并不是说这些包装在任何方面都比 Lodash 好。我们只是认为它们值得一提。

## 拉姆达

> *已经有几个很棒的功能型库了。通常，它们是通用的工具包，适合在多种范例中工作。拉姆达有一个更集中的目标。Ramda 是专门为函数式编程风格而设计的，这种风格使创建函数式管道变得容易，而且永远不会改变用户数据。*

你可以在这里找到更多关于 Ramda [的信息。](https://ramdajs.com/)

## 数学

> Math.js 是一个用于 JavaScript 和 Node.js 的扩展数学库。它具有一个支持符号计算的灵活的表达式解析器，带有大量内置函数和常数，并提供一个集成的解决方案来处理不同的数据类型，如数字、大数、复数、分数、单位和矩阵。

MathJS 功能强大，易于使用。如需文档，请点击[链接](https://mathjs.org/)。

## 懒惰的

> *Lazy.js 是一个用于 JavaScript 的功能实用程序库，类似于下划线和 Lodash，但是在引擎盖下有一个懒惰引擎，它在尽可能灵活的同时努力做尽可能少的工作。*

如果你是一个懒惰的开发者，你会喜欢这个库的。点击可以了解更多[。](https://github.com/dtao/lazy.js)

# 总结想法

如果您想简化代码，同时让您的应用程序运行得更快，Lodash 可以帮助您实现这两个目标。它也有助于解决你不想反复做的烦人的任务。

在本文中，我向您展示了如何将 Lodash 安装到 React 项目中。以及如何在 React 应用中使用 Lodash。我们还浏览了使用 Lodash 和 React 的基本示例。最后，我提到了一些 Lodash 替代品。

记住所有这些信息，是时候通过安装您选择的实用程序库将您的项目提升到另一个层次了。🤘

*最初发表于*[*https://www.upbeatcode.com*](https://www.upbeatcode.com/react/how-to-use-lodash-in-react/)*。*

*更多内容请看* [***说白了就是***](http://plainenglish.io/) ***。*** *报名参加我们的* [***免费每周简讯这里***](http://newsletter.plainenglish.io/) ***。***