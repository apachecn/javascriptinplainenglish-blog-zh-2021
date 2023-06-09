# 在 5 分钟内建立一个自定义的反应钩

> 原文：<https://javascript.plainenglish.io/build-a-custom-react-hook-in-5-minutes-2988c65e5e10?source=collection_archive---------14----------------------->

## 自定义反应挂钩快速指南

![](img/f18e907b4a0d2abc1995bbc736cd5870.png)

React 挂钩为编写 React 组件提供了一种极好的方式，而无需定义一个类。相反，我们采用功能方法来创建组件。这使得我们的代码更加模块化，因为我们不再依赖于生命周期方法来分割它们，而是根据它们的用例和目的来分割组件。

如果你是钩子新手，一定要在这里查看钩子概述。

[@sdolidze](http://twitter.com/sdolidze) 发表了一篇名为[“React 钩子的冰山”](https://medium.com/@sdolidze/the-iceberg-of-react-hooks-af0b588f43fb)的优秀深度文章，其中他一层一层地介绍了 React 提供的各种钩子。在本文中，我们将看看如何创建我们自己的自定义 React 挂钩。

# 到底什么是自定义挂钩？

钩子允许我们连接、修改和更新组件的状态和生命周期。参考 [React 文档](https://reactjs.org/docs/hooks-custom.html)，定制钩子最简单的规则是它必须总是以前缀`use`开始。自定义钩子就像一个普通的函数，因为我们可以决定它需要什么参数。自定义钩子也应该遵循钩子的所有定义的[规则。](https://reactjs.org/docs/hooks-rules.html)

构建定制钩子的主要优点是，我们能够将组件逻辑提取到可重用的函数中。这使得我们的代码更加模块化和“干净”。

# 我们在建造什么？

在 React 应用程序中持久化数据的最常见方式之一是使用浏览器自带的本地存储。我们可以把它想象成一个小的存储区域，在这里我们可以保存一些简单的键和值对来持久化一些数据。这些数据可以是任何东西，包括存储的用户配置文件属性、搜索查询，甚至是应用程序主题等偏好。

与本地存储接口非常简单。我们有两个主要功能:`setItem`和`getItem`。我们可以如下所示使用它们:

```
// Set a key-value pair
localStorage.setItem('userId', 'john_doe');// Retrieve value by key
localStorage.getItem('userId');
```

# 建筑垃圾仓库

现在，让我们开始吧。首先让我们在一个名为`useLocalStorage.js`的新文件中定义我们的`useLocalStorage`钩子。

在这段代码中，我们定义了一个新函数，它接受一个键和初始值，并将其存储在一个名为`value`的状态变量中。我们还定义了一个名为`storeValue`的函数，它有助于将函数存储到浏览器的本地存储中。

最后，我们将`value`和`storeValue`函数返回给调用者。

让我们在另一个文件中使用这个钩子，如下所示:

这里我们简单地通过导入`useLocalStorage`钩子并给它一个键来消费它。一旦组件呈现出来，我们调用`setUserId`函数来设置一个用户 ID`john_doe`。

# 从本地存储初始化我们的值

我们想从本地存储器初始化我们的值，看看我们是否有任何先前保存的值。为此，让我们对`useLocalStorage.js`中的`value`状态进行惰性初始化。

在上面的代码中，我们做了一个惰性初始化，因为与本地存储接口是一个潜在的昂贵的操作，可能会很慢。所以我们只想在应用程序第一次运行时初始化这个值。

为此，我们向`useState`钩子提供了一个函数，在这个函数中，我们试图从本地存储中检索一个键。如果存在任何值，并且我们能够将它解析成有效的 JSON，那么我们返回它。如果出现解析错误，或者没有键，我们只需返回`initialValue`。

# 提高存储价值

最后，让我们增强 storeValue 函数，将它转换成一个`useEffect` 钩子，并在存储值之前将其字符串化。

通过使用`useEffect`钩子并在依赖数组中指定`value`，我们将能够在每次`value`更新时将值保存到本地存储中。我们将`value`和`setValue`返回给我们的调用函数。

# 结论

就是这样！只用几行代码，我们就创建了一个专用的钩子来与浏览器的本地存储接口。现在，每次我们更新变量时，它都会自动保存到本地存储中。即使浏览器重新加载，我们也能够从浏览器的本地存储中检索值并初始化我们的变量。

自定义钩子在 React 应用程序中非常有用，可以简化重复的逻辑。

如果你有兴趣看看来自开发社区的一些有用的自定义 React 挂钩，请查看由[奇杜梅·纳姆迪撰写的这篇文章🔥💻🎵🎮](https://medium.com/u/a1ee806e09de?source=post_page-----2988c65e5e10--------------------------------)

编码快乐！💻

*更多内容尽在*[*plain English . io*](http://plainenglish.io/)