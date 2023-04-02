# 我们都对干净的代码有误解

> 原文：<https://javascript.plainenglish.io/clean-code-demystified-803641ca000f?source=collection_archive---------7----------------------->

## 我们都有误解，认为干净的代码是一些肤浅的代码，但这将会改变…

![](img/6fbd43fb27ca5f296c52f2577e462ab1.png)

Photo by [Walling](https://unsplash.com/@walling?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/s/photos/programming?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

写代码很简单！一个编程新手可以在几分钟内学会写代码。不相信我？请记住你的第一个“你好，世界”节目，它是多么简单。

但是编写干净的代码确实是一项很难完成的工作。这需要大量的练习和奉献。我向你保证，在这篇文章结束时，你会写出更漂亮、更干净的代码。

什么是干净代码？简而言之，就是代码容易理解，容易修改。

即使是糟糕的代码也能运行。但是如果代码不干净，它会使开发组织陷入困境。每年，由于糟糕的代码，无数的时间和资源被浪费。

如果你写干净的代码，那么你就是在帮助你未来的自己和你的同事。有了这样的代码，你就降低了你正在编写的应用程序的维护成本，并且修复 bug 也变得更加容易。

但是在学习写干净代码的时候有一个问题。问题是关于这个主题有太多的实践和技巧，可能会让人不知所措。因此，开发人员很难选择这些提示和技巧，并且经常不知所措。

让我们简化这个过程。在本文中，我们将首先讨论编写干净代码的一些优点，以便您知道我们为什么要编写特定类型的代码。

然后，我们将看看开发人员最常用的编写干净代码的五个最佳技巧或实践。

# 编写干净代码的好处

1.  更容易理解、开始或继续
2.  更适合团队入职

![](img/9d49322b65141a9e0503ccbf36338c55.png)

## 1.更容易理解、开始或继续

让我用一个简单的例子来说明这一点。假设我们在很长一段时间后回到我们的一个项目。也许，我们以前的一个客户联系了我们，并雇用我们做另一项工作。

现在，让我们也想象一下，在那个时候，我们并没有写出最干净的代码，而是做了相反的事情。在第一次看完之后，我们看到代码是多么的糟糕和混乱。而且，我们也已经可以看到从我们停下来的地方开始会有多难，并且会失去动力。

结果，我们现在不得不在项目上花费比要求更多的时间，因为我们必须理解我们过去写的混乱的代码。如果我们从一开始就编写干净的代码，我们就可以避免这种时间浪费。我们做大多数开发人员遇到麻烦时会做的事情，重新开始！

如果我们写了干净的代码，这将纠正我们的问题。也许我们需要花几分钟来阅读代码，以了解一切是如何工作的。

## 2.更适合团队入职

编写干净代码的另一个好处与第一个密切相关。它允许更容易和更快的采用。

我的意思是。让我们想象一下，我们需要雇用另一个开发人员。她需要多长时间才能理解代码并学会如何使用它？

看情况！如果我们的代码很乱，写得很差，她将需要更多的时间来完成它，就像我们在前面的例子中一样。另一方面，如果我们的代码是干净的、可读的、可理解的和简单的，她将能够更快地开始。

有些人可能会说，这不是问题，因为我们在那里引导她。但是等一下，想一想，如果你在一个更大的组织中工作，在一个大型项目或应用程序中工作，会怎么样？你只是无法向所有人解释你的逻辑是什么。

干净的代码将帮助我们把更多的开发人员带到团队中，并帮助他们立刻理解我们的代码。这不仅有助于你个人，也有助于整个组织。

简单地说，代码越干净，解释起来就越容易，混乱就越少。

我将在这里结束这一部分，但是我可以永远写干净代码的优点。只是一个没完没了的话题。

# 编写代码时要记住的要点

## 1.用缩进让代码看起来漂亮

好的代码结构合理。最简单的方法是使用空白。我们可以使用缩进、换行符和空行来使代码结构更具可读性，而不是编写精简的代码。

当我们决定接受这种实践时，我们代码的可读性和可理解性可以得到显著的提高。

然后，看一眼我们的代码就足以理解它了。让我们来看两个简单的例子。

![](img/effd09e937de416c3d8a6ba1c390d747.png)

这个世界上到底有谁准备好阅读第一个案例了。想象 10，000 行代码以同样的风格编写。真是地狱啊。

## 2.命名规格

这篇技巧是关于为变量、函数和方法使用有意义的名字。

有意义的名字是什么意思？有意义的名字是有足够描述性的名字，其他人，不仅仅是我们，将能够理解变量、函数或方法存在的目的。换句话说，名字本身应该暗示变量、函数或方法的用途，或者它包含什么。

我曾经和初级开发人员一起工作过，他们编写像这样的 HTML 类“containerrrr”或“imagesstowriteno”wtf 这是不是意味着甚至！

![](img/b8af2ca112326528cdda28b1b3750e20.png)

然而，有一些事情我们应该记住。使用描述性名称并不意味着我们可以随意使用任意数量的字符。一个很好的经验法则是将名字限制在三到四个单词内。

## 3.一个函数或方法只能执行一项任务

当我开始编码的时候，我写的函数和方法看起来就像一把瑞士军刀。他们几乎可以处理和做任何事情。其中一个后果是很难找到一个好名字。

其次，除了我之外，几乎没有人知道这个或那个功能是做什么的，以及如何使用它。嗯，有时候我也会遇到问题。所以，我不得不写说明。第三，这些功能有时很难预测。我制造了一场混乱。

然后，有人给出了这个很棒的建议。让每个函数或方法只执行一项任务。这个简单的建议改变了一切，帮助我写出了干净的代码，至少比以前更干净。

![](img/b913890d4a2bc61c054bf165fe349fbd.png)

## 4.使用注释进行澄清

不管我们如何努力为变量、函数和方法想出有意义的名字。我们的代码本身仍然不够清晰易懂。还有一些行需要进一步解释。

问题可能不在于它们难以理解或使用。相反，我们为什么要实现这个或那个函数或方法可能没有意义。

我们经常不得不用非常规的方法来解决问题。对于这样的事情，我们的代码本身会造成混乱。写一个简单的 3 到 4 行注释可以让我们的意图更加清晰。它可以帮助我们和其他人解释为什么我们使用这个代码。

因此，每当我们发现自己处于决定使用一些黑客、快速解决方案或非传统方法的情况下，让我们用评论来解释我们为什么这样做。最好用一两行文字来说明，而不是让人们自己去猜测。

但是请注意，我们应该只在必要的时候使用注释，而不是仅仅解释我们糟糕的代码。写太多注释可能会导致糟糕的代码。

我认为不好的评论指出了代码的作用，而好的评论解释了代码存在的原因。如果你不是对一段代码在做什么感到困惑，而是对它为什么在那个时刻这么做感到困惑，那么应该添加一个注释。

## 5.保持一致

当我们找到自己喜欢的特定编码实践或风格时，我们应该坚持下去，并在任何地方使用它。在不同的项目中使用不同的编码实践或风格并不是一个好主意。

它几乎和完全不使用任何编码实践或风格一样有用和有帮助。回到我们的旧代码将不会像它应该的那样流畅和自然。我们仍然需要一些时间来理解我们在那个项目中使用的编码实践，然后他们才能使用它。

最好的做法是选择一套编码实践，然后在我们所有的项目中坚持这些实践。然后，返回到我们的旧代码并在我们停止的地方继续或改进它会容易得多。

实验呢？尝试新的编码实践是一件好事。它可以帮助我们找到更好的工作方法。然而，最好在单独的实验项目或练习中试验不同的实践，而不是我们的主要项目。

# 关于编写干净代码的最终想法

我们讨论的实践可能不是影响最大或结果最显著的实践。然而，它们是有经验的开发人员最常使用的。

这就是为什么我选择与你分享这个。我希望这些实践或技巧足以帮助您开始编写干净的代码。

现在，就像所有事情一样，最重要的是开始行动。因此，至少选择一种做法，并尝试一下。

快乐干净的编码！😃

*更多内容看*[***plain English . io***](http://plainenglish.io/)