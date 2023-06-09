# 可以在 React 中使用的所有类型的组件

> 原文：<https://javascript.plainenglish.io/all-types-of-components-that-you-can-use-in-react-cee21b816fc4?source=collection_archive---------9----------------------->

## 你应该知道的组件。

![](img/921efd6ad9a49f711bdbf9029396b0b2.png)

Photo by [Scott Graham](https://unsplash.com/@homajob?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

组件的概念很容易理解。基本上，它是一个可视化的软件元素，有自己的状态，接收一些属性，实现自己的渲染逻辑。但是所有的成分都一样吗？我们可以对它们进行排序或将其划分为组件类型吗？

本文试图介绍我们可以在 React 中使用的组件类型。我将把这些类型分为两类，行为分类和结构分类。

# **行为成分的类型**

根据组件将执行的行为类型，我们可以将组件分为无状态、有状态、纯组件或特设组件。因此，您将了解并理解这些类型的组件:

## 有状态组件

这种类型的组件是最常用的。这种类型的组件的主要特征是它们在类中使用封装，有一个它们定义和更新的状态，并且属性和状态的每次改变都调用 render 方法。

## 无状态组件

这个组件是最常见的组件:有状态组件的简化版本。这些组件被定义为普通 js 中的函数，不具有状态，也不与状态一起工作。这些类型的组件处理的唯一数据是接收到的 props，它也不允许覆盖它们生命周期的方法。这些组件的优点是易于编写、易于测试，并且可以提高性能。

## 纯成分

就其定义而言，这种类型的组件类似于有状态的组件。它们也被实现为类，但在这种情况下，它们将从 React.PureComponent 扩展而来。与无状态组件一样，这种类型的组件不定义状态，纯粹只是一个可视化组件。这些组件经过优化以获得更好的渲染性能，因为它们仅在检测到其属性发生变化时才会发生变化，并且这些属性不同于以前的值。

## 高阶组件或特设。

这种类型的组件是 React 应用程序中使用的设计模式。这个生态系统中的设计模式让我想起了[装饰模式](https://en.wikipedia.org/wiki/Decorator_pattern)。

高阶组件(HOC)接受另一个参数组件，扩展其功能并返回一个具有扩展功能的新组件。如果特设的属性发生变化，特设将再次呈现，并更新包装在其中的组件。

这种类型的组件用于实现常见的功能，如分页、截取和修改呈现、调用 API、提供包装的组件以及控制表单的输入。

这种类型的组件用于 React 生态系统中广泛使用的库中，比如 react-redux 和 react-redux-form。基本上，这是一个很好的方法来分离功能，扩展组件的功能，并在整个应用程序中重用代码。

# **结构部件的类型**

这些组件在技术上并不对应 React 中的任何 API 元素、类或函数。它们只是纯粹的概念。这种分类旨在组织我们的应用程序，使其开发起来更简单、更直观。这种分类不是 React 标准，而是社区标准，允许我们在应用程序中定义架构。

## 视觉组件

这些类型的组件应该只关注 UI 应该如何呈现。这些类型的组件可以由其他可视元素组成，通常包括样式和类。其渲染所涉及的所有数据都必须通过 props 接收，因此它必须独立于对外部服务的调用。这些组件通常是无状态类型的，因为它们不需要状态，并且必须通过它们的 props 来管理它们对父组件的动作。

## 容器组件

这些组件必须把接口放在一边，照顾功能部分。它们只是其他组件的容器，负责管理交互逻辑和数据逻辑，对外部服务进行必要的调用。与前面的不同，它们通常管理自己的状态，是组件树层次结构中的重要节点。

我浏览了 React 中组件的不同分类和类型。这些是任何基于 React 的 SPA 架构中最常用的类型。因此，我鼓励您在开发中开始使用它，并告诉我们您在项目中实现前端架构的经验。

*更多内容尽在*[plain English . io](http://plainenglish.io/)