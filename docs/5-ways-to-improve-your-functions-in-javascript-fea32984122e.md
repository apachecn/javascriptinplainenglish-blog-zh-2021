# 提高 JavaScript 功能的 5 种方法

> 原文：<https://javascript.plainenglish.io/5-ways-to-improve-your-functions-in-javascript-fea32984122e?source=collection_archive---------3----------------------->

## 通过将这些方法应用到您的函数中，让您的 JavaScript 生活变得更加简单

![](img/87ca9b0e776de329c0e84e52a8e4a1cc.png)

当调用 JavaScript 函数时，几乎总是需要提供参数。但是如果你不小心的话，这些很快就会变得一团糟。所以我列出了一些方法，让你作为 JavaScript 开发人员的生活更轻松，让你的代码更容易阅读，让你的同事也能更快地阅读你的作品！

想象一个有 3 个参数的基本函数，它对你的数据做了一些神奇的处理并返回一个结果。很简单，对吧？我相信您可以在您的代码中找到符合该描述的函数。我要用一个虚构的函数来做一些愚蠢的事情。

这会输出`A-6`，但是你不能通过阅读参数来知道。您也许可以通过更改函数名来解释这一点，但这只能提高这么多的可读性。

# 1.正确的函数和变量名

这似乎是显而易见的，但是拥有合适的函数和变量名可以说明很多问题。`myFunction()`根本不会告诉你任何事情。在这种情况下，什么是一个好名字？大概是类似`generateSystemCodeFromBaseValue()`的东西。

是的，那很长，但是说真的，那有关系吗？我们在任何情况下都会受到字符长度的限制吗？

最重要的是，无论何时你发布你的代码，你都应该最小化它，这样无论如何都会去掉大部分的函数名。

所以要用合适的名字！它们不必很短，必须是描述性的。你必须通过阅读名字来知道一个函数是做什么的。这样做可以防止你实际上需要一个注释。

# 2.命名参数

JavaScript 中没有命名参数。但是，您可以使用对象符号来实现它。如果在函数和调用行中都指定了对象表示法，则将实现命名属性。我已经重写了相同的代码来命名参数。

正如您所看到的，您已经可以理解这里发生了什么，并且您实际上知道您正在发送什么类型的数据。

如果你改变对象中参数的顺序，那也没关系，不管怎样，最终结果都是一样的。

# 3.默认值

一旦将函数调用配置为使用带有上述命名参数的对象表示法，您也可以轻松地开始指定默认值。您只需要定义默认值应该是什么，并且您可以通过调用函数来覆盖这些值。

这意味着您可以指定一些默认值，而不必总是知道在调用函数时要指定什么。我在前面的代码中添加了一些默认值，并去掉了一个参数，因为我对默认值很满意。

最终结果还是`A-6`。

# 4.删除长函数

如果你的函数做多件事，你应该把它分成两部分，并为它们定义合适的名字(见第 1 点)。

让我们看一下上一步的代码，这是一个简洁的函数，只做一件事，并且不需要任何注释就很容易理解。

然而，假设类别“代码”是基于我们正在做的乘法的结果来定义的。即使我们的代码中没有其他地方需要计算这个，出于可读性的原因，您仍然应该将它放在一个单独的函数中。在这里比较两种选择。第一种方法是将所有内容都压缩在一个函数中，第二种方法是将它分成两个函数。

我认为第二种选择会干净得多。不仅不需要 if/else 语句，您还可以使用`return`来跳出函数，以便更清晰地阅读。

这也不容易出错。使用 if/else 语句，您有时会忘记添加“else ”,而只是在稍后添加另一个 if 语句，这可能会导致您覆盖变量。因为你必须开始使用`let`而不是`const`，它实际上被允许覆盖它。

[](/how-to-prevent-unexpected-variable-mutation-in-javascript-2612b898732c) [## 如何防止 JavaScript 中意外的变量突变

### 所以当你使用 JavaScript 时，你可以灵活地用任何东西覆盖任何变量。你怎么…

javascript.plainenglish.io](/how-to-prevent-unexpected-variable-mutation-in-javascript-2612b898732c) 

# 5.返回多个变量

实际上，您可以用 JavaScript 返回多个变量，就像您可以为一个函数提供多个命名参数一样。假设你可以从函数中返回类别和值，而不仅仅是一个代码，那么你可以返回多个变量。

这样你就可以在函数之外使用这两个变量，而不会有任何问题，也不需要修改代码！那不是很容易吗？

## 最后

JavaScript 代码有很多容易成功的地方，但是这 5 个应该可以帮助你写出更好的函数！

*更多内容尽在*[***plain English . io***](https://plainenglish.io/)