# 如何在 JavaScript 中分解一个昂贵的计算任务

> 原文：<https://javascript.plainenglish.io/how-to-break-up-an-expensive-computation-task-in-javascript-446801d646ca?source=collection_archive---------11----------------------->

![](img/4c4de5c80887e5a69ddce6417c12265f.png)

JavaScript 是单线程语言，这意味着如果我们开始完成长时间运行的任务，它会阻止应用程序的另一部分完成。在前端方面，这意味着用户界面将被冻结，这对用户来说肯定是一个恼人的部分。在服务器端，这意味着服务器停止处理来自用户的新请求，并且变得没有响应。我们作为开发人员总是试图减轻它，并且应该记住它。

避免这种情况的一种方法是将长时间运行任务的完成转移到单独的 web workers 中(在客户端)，或者用它们自己的事件循环产生单独的子流程(在服务器端)，但是还有另一种方法来完成它——使用 JavaScript 的异步行为。

# 打破客户端长期运行的流程

这里`Promise`和`requestAnimationFrame`一起来玩。

让我们想象一下，我们有一个使用 CSS 规则的动画矩形:

![](img/55119d7ea7588cc4b7d85fc2c4c67a27.png)

我们还添加了一个无限循环的脚本。我相信，你知道当我们开始完成这个脚本时，页面会变得没有反应，我们在控制台中看不到应该由`console.log`打印的`Here`字

```
function completeInfiniteTask(){
     while(true){}
}
completeInfiniteTask();
console.log('Here');
```

![](img/196116cda692a493498a75b190fb1c1c.png)

好吧，让我们开发`nextFrame`函数，它将有可能中断这个无限循环，并为完成应用程序的另一部分腾出空间。看起来是这样的:

```
function nextFrame() {
    return new Promise((res) => {
         requestAnimationFrame(() => res())
    });
}
```

在这种情况下，我们明确要求浏览器绘制下一个动画帧，一旦浏览器绘制了这一帧，`Promise`就会被解析。

当然，我们需要重写我们长期运行的任务，并在`async`函数中将其输出，并定义我们希望暂时中断的确切时间。例如，我们可以在每个第 5 步中断这个循环:

```
async function completeInfiniteTask(){
     let count = 0;
     while(true){
          if (++count % 5 === 0){
               await nextFrame()
          }
     }
}
completeInfiniteTask();
console.log('Here');
```

在这段时间里，JS 有足够的时间同时完成长时间运行的任务并绘制动画矩形的下一帧，只是因为 JS 不仅是单线程语言，而且还支持异步。

![](img/7a2f9ea65198f547fc7ebdae9df919fc.png)

这里`console.log`几乎立即打印`Here`，矩形动画没有延迟，尽管在后台 JS 仍然继续处理无限循环，因为每个第 5 步都为应用程序的其他部分处理让路。

# 在服务器端中断长时间运行的流程

方法实际上是相同的，但是`requestAnimationFrame`在服务器端不可用，它只包含在浏览器 API 中。但是在这种情况下，我们可以用`setImmediate`来代替:

```
function nextFrame() {
    return new Promise((res) => {
         setImmediate(() => res())
    });
}
```

# 它可能用在什么地方？

让我们想象一下，我们正在开发一个应用程序，用户上传一个 CSV 文件，应用程序需要解析每一行，在这个过程中，我们应该显示一个进度条。使用`nextFrame`函数是一个很好的选择，在解析 N 行之后，我们可以中断解析过程并显示进度条的实际状态。

这种方法也有`TensorFlow`这样的框架，允许开发者打破模型学习的长时间运行过程。

*更多内容尽在*[plain English . io](http://plainenglish.io/)