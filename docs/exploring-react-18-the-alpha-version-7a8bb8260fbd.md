# 探索 React 18，Alpha 版本

> 原文：<https://javascript.plainenglish.io/exploring-react-18-the-alpha-version-7a8bb8260fbd?source=collection_archive---------16----------------------->

![](img/53dad57f639dd30194c201b53aa5fd4b.png)

React 核心团队已经公布了 React 18 alpha 版本。稳定版的发布还有几个月的时间。该团队已经邀请社区成员加入 GitHub 讨论工作组(WG ),以获得下一个主要版本的第一感觉。

对于 React 爱好者来说，这是一个令人高兴的消息，当有许多功能推出时，这一消息更令人高兴。对于那些一直关注 React v17 的人来说，React v 17 没有为开发人员带来新的特性，但是进行了内部改进，提高了库的效率。

## 新的改进和并发模式

显然，React 18 附带了新功能，但请注意，这些功能目前正在开发中，目前并不打算供开发人员在生产应用中使用，而是在遵循工作组讨论的同时进行实验。测试版仍然需要几个月才能发布。但是，在为稳定版本做准备时，熟悉一下新特性是有好处的。

React 18 带有“并发功能”，基本上启用了一种选择加入机制，允许开发人员升级到 React 18，而不中断他们的应用程序。当前版本设计为运行不同版本的 React。这是通过在多个版本中多次呈现 UI 来实现的。

## 升级到 React v18

安装(或升级)React 18 是显而易见的。我试图将我正在开发的两个现有的 React 应用程序升级到 React 18。结果是 17.0.2 版本能够升级到 React 18，而 16.14.0 版本没有成功。它一直抛出:*错误:无法在未安装的组件*上找到节点

出于某种原因(我仍在研究)，我无法升级到与我们心爱的 NPM 反应 18。在尝试升级 React 16 和 17 应用程序时出现了一周的错误。无法在 GitHub 上评论工作组的讨论来强调这一差距，因为我不是被选中的人之一(lol)。工作组讨论仅限受邀者参加。

然而，yarn 完成了这项工作。我们简单地添加了 React 和 ReactDom 18 个 alpha 版本。如果你想开始一个新项目。很简单。` ` yarn create react-app app-18 ```。它将创建 React v17.0.2 应用程序。然后用 yarn add 运行升级。对于现有的应用程序，只需运行命令。

```
yarn add react@alpha react-dom@alpha
```

新建根 API

按照上述步骤，您的应用程序将会启动，但如果您在浏览器开发工具上检查您的应用程序，则会发出如下警告。

*index.js:1 警告:React 18 中不再支持 ReactDOM.render。请改用 createRoot。在你切换到新的 API 之前，你的应用会表现得像运行 React 17 一样。了解更多:*[](https://reactjs.org/link/switch-to-createroot)

*因此，我们继续将应用程序的顶层更新为:*

*老路:*

```
*`import React from ‘react’;
import ReactDOM from ‘react-dom’;
import App from ‘./App’;ReactDOM.render(<App />, document.getElementById(‘root’));</code>*
```

*新方法:*

```
 *import React from ‘react’;
import ReactDOM from ‘react-dom’;
import App from ‘./App’;const root = ReactDOM.createRoot(document.getElementById(‘root’));
root.render(
<App /> );</code>*
```

> *与旧方法不同的是，呈现从根开始，而不是从 React DOM 呈现。这一变化对 ReactDOM.hydrate 有影响，它用于 SSR 以加快页面加载和 SEO 优化。正如 React 核心团队所解释的，ReactDOM 上有一个新的 hydrateRoot API。它不需要单独的渲染调用。我们可以看到它接受了第二个论点，即 JSX。*

```
*const root = ReactDOM.hydrateRoot(document.getElementById(“root”), <App />);*
```

*我们还可以在根组件中添加渲染回调函数。这些是新的根 API 中的一些变化。现在，我们在探索 React 18 附带的新功能方面处于领先地位。*

*React 18 的顶级功能包括开箱即用的改进，如自动批处理、startTransition API、内置 React Lazy 支持的 SSR。*

## *较少渲染的自动批处理*

*前端开发人员知道，我们处理的一个主要问题是屏幕为用户更新了多少次。渲染越少，用户体验越好。以前的自动批处理是手动完成的，但在这个版本中，它是默认完成的，以提供内置的改进。批处理基本上是将我们的更新组合成一个单独的重新渲染。*

## *startTransition API*

*是一个令人兴奋的特性，它支持开发流畅且响应迅速的 UI。它使我们能够包装非紧急更新，这样当我们在 UI 上执行其他操作时，我们可以向用户显示更紧急的更新。*

```
 *import { startTransition } from ‘react’;// Urgent: Show what was typed
setInputValue(input);// Mark any state updates inside as transitionsstartTransition(() => {
// Transition: Show the results
setSearchQuery(input);
}); </code>*
```

*还有其他功能，如 *useDeferredValue* 让我们推迟更新屏幕上不太重要的部分，*<suspendelist>*让我们协调加载指示器出现的顺序，以及带有选择性水合的 SSR。*

*所有这些特性在工作组关于 GitHub 的讨论中都有很好的概述。在我们等待稳定版本的时候，请注意，在 React 18 的第一个稳定版本发布之前，这些功能可能会进行调整以适应社区的意见。*

**更多内容尽在*[***plain English . io***](http://plainenglish.io/)*