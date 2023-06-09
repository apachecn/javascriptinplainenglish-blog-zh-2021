# Jest:编写你可以依赖的单元测试

> 原文：<https://javascript.plainenglish.io/jest-writing-unit-tests-you-can-depend-on-8028e159e678?source=collection_archive---------13----------------------->

## 我们都知道我们应该写测试。但是你从哪里开始呢？

![](img/5e22c8e11a24d93010b3da557f0803ea.png)

Like a good set of wrenches, unit tests are essential to any Software developers toolkit. Photo by [Nina Mercado](https://unsplash.com/@nina_mercado?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

我一直想在一个大家都写测试的环境下工作。对我来说，这感觉就像圣杯一样——如果做得好，会给我(和项目中的每个人)信心，相信我所做的更改没有破坏代码库中的其他东西。它们对我的另一个爱好——CICD 来说是必不可少的，这也意味着我可以让新手不受限制地访问代码库，知道如果/当他们破坏了一些东西，测试将会失败，然后无法投入生产。但就像圣杯一样，它们总是有点遥不可及，因为迄今为止我工作过的所有地方都将快速交付置于长期稳定性之上。

最后，我找到了一个我们应该写测试的地方。但现在的问题是‘我们如何写出好的测试’？

为了使测试有效，它们需要真实地反映组件在现实生活中的使用情况。如果函数只将两个数字相加，测试会相当简单。但是如果组件包括交互性，那么测试应该包括交互性，因此会更加复杂。例如，一个选择组件应该有初始值或占位符的测试，点击事件，可能还有样式等等。

这篇文章并不打算详尽列出你可以在 [Jest](https://jestjs.io/) 中做的所有事情。它也不是使用[测试库](https://testing-library.com/)的权威指南。但是它的目的是让你知道在不同的场景下应该测试什么。随意组合&匹配方法以满足您的需求。

## 单元测试与集成测试

在我开始给出建议之前，熟悉一下行话可能是个好主意。

有许多类型的测试。如需详细指南，请参考[这篇非常有见地的堆栈溢出帖子](https://stackoverflow.com/questions/520064/what-are-unit-tests-integration-tests-smoke-tests-and-regression-tests/520116#520116)。

在这篇文章中，我将讨论单元测试——测试特定功能的小而简洁的测试(有一个狭窄的焦点)。我们将模拟所有的外部函数调用和依赖，以使我们的测试干净并且总是可重复的。

它们不同于集成测试，集成测试被广泛定义为覆盖多个系统的测试(比单元测试有更广泛的关注点)

## 堆栈

我的测试堆栈由 2 个(+1)核心工具组成:

*   Jest —测试框架
*   [测试库](https://testing-library.com/docs) — UI 测试库
*   TS Jest —让 Jest 与 Typescript 一起工作

这 3 个工具处理从编写和运行测试、与 DOM 交互(如果需要)到导出测试覆盖([到 Sonarcloud](/making-sonarcloud-play-nicely-with-jest-fa271f559024) )的所有事情

现在让我们开始吧。

## 简单的功能

从一个将两个值相加的函数开始。这里的测试同样简单。当我用 2 和 3 作为参数运行函数时，它应该返回 5。如果是的话，我们知道代码是有效的。如果没有，我们知道我们有一个问题。

Shows the add function and how to test it — expect 2 + 3 to equal 5.

这里我只有一个测试，但是你可以为同一个函数编写多个测试。目标应该是像在现实生活中一样测试这个功能。

如果您有一个 React 组件，这个过程非常相似。测试库提供了渲染组件的工具。我们测试它的渲染是否没有错误，并检查它的外观——例如，它里面有文本吗？

A simple component with text inside. You wouldn’t be building the component in the test (you will be importing it) but it serves to demo the test.

## 调用其他函数的函数

当我们拥有调用其他函数的函数时，事情会变得稍微有趣一些(并且更有生活气息)。

这里我有一个调用另一个函数从 API 端点获取用户的函数。

这里的挑战是我们如何保证 fetch 调用总是有效的。如果我们不控制端点，这将尤其具有挑战性。这就是[笑话嘲讽](https://jestjs.io/docs/mock-functions)的用武之地。

模拟允许我们模仿/覆盖一个函数的响应。这使我们能够完全控制将什么数据传递到我们要测试的代码中。记住，在单元测试中，我们只是试图在有限的范围内测试我们的代码。我们不写 API 或集成测试。保持简单！

在上面的测试中，我模拟了端点文件中的`getUsers`函数。我用一个简单的承诺覆盖了 fetch 调用，该承诺返回一个由 3 个字符串组成的数组。我知道如果数组中有 3 个字符串，`countUsers`函数应该总是返回 3。

更进一步，如果我试图调用的函数带有参数，我应该编写测试来确保正确的参数被传递给它。

在下面的测试中，你可以看到我们模拟了`getUser`函数，和以前一样，我测试了函数`getUserName`的结果。但是这里我们也检查了模拟`getUser`函数是否被调用，以及调用它的参数是什么。

在我们的例子中，这将始终是`1234`，因为我为演示硬编码了它。但是在现实生活中，你会有动态变量作为参数，这就是这种测试特别有价值的地方。

上面的测试还引入了另一种技术，`jest.requireActual`。您可能会遇到这样的情况，您只想模拟文件中的一些函数，而不是所有函数。`jest.requireActual`允许我们获得“实际的”文件，当与 spread 操作符配对时，我们只模拟我们需要的函数——在本例中是`getUser`。

模仿函数允许我们缩小测试的范围，保持它们的一致性，使它们更容易阅读和维护。

## 修改状态的函数

我们的功能经常与状态交互。下面是一个按钮组件，当单击它时，调用一个 Redux 动作，当与一个 Redux(为简单起见省略)配对时，将更新 Redux 状态。

为了模拟涉及状态的交互，我使用`redux-mock-store`和`react-redux`来包装组件并模拟初始状态。

在上面的例子中，当按钮被点击时，我调度 Redux 动作。`store.getActions`返回所有动作调用的数组，我们可以根据预期对其进行测试。

注意:不要试图修改`getActions`响应。编写修改测试结果的代码会引入错误，使测试更难阅读和维护。

## 事件

在前面的段落中，我提到了 click 事件，它对按钮很有用，可能是您最常用的事件。但是我们可以使用许多其他的事件，包括`drop`、`change`、`keyup`、`keydown`和`paste`(这里是[的完整列表](https://testing-library.com/docs/dom-testing-library/api-events))来模拟交互性。

在前面的例子的基础上，我有一个文本输入组件，当值改变时，它会更新状态。

为了测试这一点，我呈现了组件并检查是否设置了占位符属性。测试库有一个名为`type`的`userEvent`，它模仿输入字段中的输入。

同样，我们得到了返回所有动作调用的 Actions。我们不希望测试立即完成，而是等待一段时间。测试库有一个 [](https://testing-library.com/docs/dom-testing-library/api-async/#waitfor) `[waitFor](https://testing-library.com/docs/dom-testing-library/api-async/#waitfor)`函数，可以与 async/await 一起使用，以等待条件为真(默认为 1s，但可以配置更长时间)。这对于不会立即发生的组件更改非常有用。

## 每个测试

当编写测试时，我优先考虑可读性，而不是枯燥。我希望能够将我的测试交给另一个人，他们可以一步一步地通过测试和代码测试，并能够找出发生了什么。

但是就像所有规则一样，也有例外。

对于几乎相同但有一些小变化的测试，我可以使用 test.each，这是一个 jest 函数，允许我们多次运行测试，每次使用不同的参数。

回到前面的加法函数示例:

如果我们想将不同的参数传递给我们的 add 函数，我们可以使用`test.each`。有[不同的方法](https://jestjs.io/docs/api#testeachtablename-fn-timeout)来指定 test.each，但我更喜欢表格方法，因为我可以指定列标题，并在测试标题和参数中使用标识符。

在上面的例子中，我用不同的输入参数运行了 3 次测试，并测试了每个参数的结果。

这是一个过于简单的例子，但在现实生活中，这种方法可以在许多情况下使用。例如改变函数参数或初始状态值。这意味着我不必复制和粘贴测试代码。

虽然这不是所有 Jest 和测试库功能的扩展列表，但它有望让您初步了解您可以(并且应该)测试什么。最终，单元测试是工具箱的一部分，工具箱包括其他类型的测试，您希望能够依靠这些测试来捕捉流氓错误。拥有良好的测试覆盖率可以更容易地让新人加入进来，知道如果他们破坏了什么，就会被发现。

最后，永远不要认为测试已经完成。你可能有 100%的覆盖率，但这并不意味着你已经考虑到了每一个用例。当组件因为用户做了你没有想到的事情而崩溃时，你应该将这个工作流添加到测试中。现在，当您编辑或更新组件时，您知道它必须通过新的测试用例才能为您的所有用户工作。

感谢您花时间阅读本文

我希望你觉得这很有用

大卫

高级前端开发人员@ [TripActions](https://tripactions.com/)

*更多内容看* [***说白了. io***](http://plainenglish.io/) *。报名参加我们的* [***免费周报在这里***](http://newsletter.plainenglish.io/) *。*