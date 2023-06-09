# JavaScript 中的函数式编程与面向对象编程

> 原文：<https://javascript.plainenglish.io/javascript-functional-vs-oop-fb5fbf15a35d?source=collection_archive---------0----------------------->

## 对两者利弊的介绍

![](img/e83fd26babe9fb9dd0d02abbb878f326.png)

Photo by [Brendan Church](https://unsplash.com/@bdchu614?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

编写代码有大量的范例。没有一种范式比另一种更好——它们都有各自的优点和缺点。其中最流行的两种是面向对象编程和函数式编程。

这篇文章将向你展示我如何编写一个小的计算器应用程序，一次是功能性的，一次是面向对象的。我们将讨论这两种范式的典型特征以及优缺点。玩得开心！

# 这两种范式的区别是什么？

**这是重要的基础知识。**
要解决任何问题，你不必致力于一种范式。实际上，您可以实现任何类型的任何东西——面向对象的或函数式的。然而，了解两者之间的区别是很重要的。

## 如何识别面向对象？

用这种方式写代码，一切都围绕着对象。代码的中心是“事物”——例如，一个人、一个数据库连接或一个输入字段。我们实际可以处理的“事物”被称为**实例**。

在大多数面向对象编程语言中，所有实例都有一个蓝图——类。我们也可以在 JavaScript 中使用它们。你可以用一句话来描述 OOP:我们创建某种类型的“事物”。当然，这是非常简化的。这里有一个例子。

```
class Person { … }const max = new Person()
const carl = new Person()
```

卡尔和马克斯都是实例，但他们有相同的蓝图。这意味着它们具有相似或相同的属性和方法。除了创建共享属性的实例之外，类还可以用来构建代码。类中的静态方法可以在没有实例的情况下使用。对这样一个方法的调用通常是这样的:`Person.greet()`。

您可以通过 class 关键字来识别面向对象。

## 怎么能认可函数式编程呢？

与 OOP 不同，在函数式编程中，我们没有拥有自己状态的“事物”——这正是我们想要避免的。

没有实例的蓝图。我们把想要实现的任务尽可能分解成功能。但不是任何函数——理想是所谓的“纯函数”。

这意味着函数对相同的参数返回相同的结果。相信我，你在学校就知道这个概念。

如果在 f(x) = x 中为 x 传递值 2，结果是 4——无论何时传递。该功能不受时间或任何其他条件的影响。这样的函数很棒，因为它们是可预测的。

好的函数也不会改变全局状态。如果是这样，函数 A 中的逻辑错误可能会导致函数 B 中的程序中止——因为 B 取决于 A 被破坏的状态。只使用函数构建所有东西可能看起来很原始。这就是为什么函数式编程喜欢使用一些小技巧——函数调用函数，函数相互连接，函数返回函数，或者把它们作为参数。
功能无处不在！

你可以通过函数识别函数代码(惊喜！).而且由于这些函数有很小的任务——代替了函数“addNumbersAndPrintThem 它们”，出现了“addNumbers”和“printNumbers”另一个特点是几乎没有全局变量。

# 代码示例

这是一个简单的应用程序，从一个文本字段中添加并输出两个数字。为此，我编写了两次 JavaScript 代码——一次是功能性的，一次是面向对象的。重要:我并不是说这个代码是理想的。

关键是要把概念表达清楚。尤其是在这个例子中，面向对象的方法似乎有些过火。

这两个版本的代码都使用这个 HTML 代码:

首先，功能代码:

功能——一切都是功能。此外，值得注意的是，根本没有全局变量。如果你从头到尾看代码，它看起来像是一个逻辑结构。

首先，读取值，然后将它们相加，然后输出。但是我们可以反过来安排功能——没关系。所有函数都是纯函数，因此它们不依赖于另一种状态，而是可预测的。

在我看来，函数式编程是实现这个小应用程序的极好方法。代码是干净的、精简的和可预测的。但是我们马上就会明白为什么这也是一个缺点。

让我们首先看看面向对象的方法。

如果您已经对 OOP 有所了解，那么您现在可能会问自己:
“*为什么路易斯会这样做，而且没有什么不同？*”。
这是一个合理的问题——诚然，我一直在思考如何最好地用面向对象编程来建模代码。

一开始，我提到了面向对象是基于现实的——这可能是失败的原因。因为到了*哪个现实*？也许会添加任意数量的输入字段，这样就可以在类 Form 和 inputField 之间创建一个 1:M 关系。

也许这个应用程序会保持现在的样子——那么一个单独的表单类就太过分了。但是，也许代码会变得更加复杂——然后将处理函数转移到 Form 类中会更合适。

建模中没有对错之分——尤其是如果没有给出默认值，就会导致大问题。你觉得直观的东西，团队中的其他开发人员可能一点也不觉得连贯。

# 两种范式的利弊

现在您知道了这两个范例——如何识别它们以及它们在代码中的样子。然而，代码示例并没有展示所有的东西——尤其是范例的缺点。以下是你应该知道的。

## 面向对象编程的好处

有了这种范式，我们试图用现实世界中的“事物”来模拟自己。类、实例、关系船和继承使得建模变得容易——通常，类应该是什么是完全直观的。

代码被分成几大块——类是中心。它们包括多个属性和方法。我们可以将它们映射到各自的类，而不是在一个文件中包含数百个函数。

## 面向对象的缺点

有非常多的方法来建模。类应该是什么并不总是直观的。OOP 模型会变得非常复杂。因此，当与多个开发人员一起工作时，如果想法不同，就会出现问题。

如您所见，OOP 代码要长得多。这并不罕见——在更复杂的例子中，情况要糟糕得多。许多类不仅包括构造函数、方法和属性，还包括 getter 和 setter 方法。OOP 需要大量样板代码。

意大利面条式代码——这个问题不仅仅发生在 OOP 中。但是通过关系、继承、多态和抽象类，混淆会很快出现。

# 函数式编程的优势

一开始，函数并不是很复杂——它们是一个绝对的基本概念，即使是初学者也知道。

只是后来才有了诸如类之类的概念。这是我们甚至在代码中应该遵循的顺序。大型项目中较小的任务可以通过函数快速解决。

但是，函数不仅更容易让人绝望，而且更容易被预测。尤其是如果我们坚持“纯函数”的理想。如果我们把问题分解成尽可能多的小函数，我们就能精确地搜索和发现出现的错误。

此外，函数可以非常重用。在许多项目中，相同的函数被反复使用——例如，对数组排序、比较大小或发送 HTTP 请求。因为它们不是复杂的结构，所以通常可以无缝地转移到完全不同的程序中。

## 函数式编程的缺点

我刚才说实际上每个人都理解函数。但是函数式编程不仅仅是“简单”的函数。这种范式还提供了可能因语言而异的抽象概念——函数作为参数、函数作为返回、currying、单子、高阶函数等等都是与函数风格相关的术语。

在 OOP 中，规则是为每个类创建一个文件。但是我们用这些小功能做什么呢？将它们都放在一个文件中是不可取的——为每一个功能准备一个单独的文件也是不可取的。因此，我们必须找到一个可以理解的，明确的妥协。

但是首先，我们必须为每个函数找到一个好名字。虽然我们通常以事物命名我们的类，但是我们有相当多的函数执行小的，甚至是相似的任务。

OOP 中的对象通常有自己的状态。这有助于封装数据，但也解决了在哪里存储我们的状态。如果我们的代码只包含函数，这可能会很困难。这也正是 Redux 这样的库流行的原因。

# 现在用什么？

我觉得没有对错。面向对象本身并不比函数式编程更好或更差。Java 和它的 OOP 在学校和大学里很受欢迎。原因是任务大多是真实世界的情况。一个有几个房间的公寓或一个有几个顾客和产品的商店可以用一种简洁的面向对象的方式建模(这些是我在 CS 课上的真实练习)。

然而，实际上，并不是所有的编程任务都是这样的。通常，没有 UML 图或实体模型——建模依赖于程序员。

我使用下面的方法:尽可能多的功能性编程。不管有没有类，基本函数就是函数或方法——顾名思义。是否将它们绑定到对象甚至可以在开发过程中决定。

## JavaScript 案例的选择

至此，我已经笼统地谈了两种范式的优缺点。但是 JavaScript 呢？严格来说，JS 是多范式的。例如，这可以从存在类的事实中看出，但与 Java 不同，不存在使用它们的“义务”。

我发现 JS 有趣的一点是——“class”关键字只是语法上的糖。在后台，类实际上是基于原型继承的。在我看来，你注意到了一点——与面向对象优先的语言如 Java 相比，JS 中的面向对象似乎有点“落后”。

因此，尽管有类、继承、构造函数等等——对于完整的 OO 编程，我更喜欢 TypeScript。以我的经验来看，OOP 风格在 JS 社区中也不是很常见。对我来说，旧的 React.js 是我必须使用类的唯一地方——与基于函数的组件相比，钩子的乐趣是巨大的，因为替代物是巨大的。

另一方面，JS 为函数式编程提供了很好的支持——map、filter 和 reduce 只是一些实用的特性。用 JavaScript 进行函数式编程很有趣——我只能建议每个人都掌握它，从函数的角度解决尽可能多的问题。

[**加入我的简讯保持最新**](http://eepurl.com/hacY0v)