# 常见的 JavaScript 面试问题

> 原文：<https://javascript.plainenglish.io/common-javascript-interview-questions-8af095ed24f0?source=collection_archive---------9----------------------->

![](img/0a1735503215afbad5bc2254544ab177.png)

## 问:作用域、闭包和回调是如何一起工作的(ES6)？

**范围**指的是我们代码中变量的可访问性。范围主要有两种:**全局**和**局部**。

**全局作用域的**变量在函数外部用 *var* 、 *const、*或 *let* 声明，可以从代码中的任何地方访问。JavaScript 中只有一个级别的全局范围。

**局部范围**有两级范围:**功能**和**块**。

每次创建函数时，都会创建一个**闭包**。它封装了函数内部的变量，创建了一个**局部作用域**，同时允许访问函数外部作用域中的变量。单独声明的函数不能访问另一个函数的作用域。

**函数级** **作用域**变量在函数内用*var* 声明。该级别中的变量可用于该函数及其任何嵌套函数。

具有**块级范围**的变量只能用 *const* 或 *let 声明。*这些变量被限定在创建它们的块(即函数、if 语句或循环)范围内，不能在该块之外访问。嵌套的函数和块可以访问它们。

**回调**是作为参数传递给另一个函数的函数。回调中声明的变量将不能在父函数的作用域(或任何外部作用域)中使用。回调函数可以访问父函数的所有变量。

## 问:var，let，const 有什么区别？

你知道会这样，对吗？很长一段时间以来， *var* 是 JavaScript 中声明变量的唯一方式。直到 ES6 (ES2015)才推出 *let* 和 *const* 。**var*var*有很多问题，现在认为最好不要使用它—** 让我们找出原因。

在用 *var* 声明一个变量之后，JavaScript 将允许您通过简单地用另一个值再次声明它来覆盖同一个变量。如果我们用 *let* 或 *const* 来尝试，我们会得到一个语法错误。用 *var* 创建的变量，如果在声明之前被调用，也不会抛出错误，它只是被 *undefined* 。而用 *const* 或 *let* 创建的变量在声明前被调用将抛出引用错误。用 *const* 或 *let* 声明的变量被认为是块范围的，只能在创建它们的块内访问。如果在一个块中用 *var* 声明了一个变量，那么它将可以在父块之外被访问(如果块不运行，该变量将是*未定义的*)。

但是*常量*和*常量*有什么不同呢？它们在各方面都很相似，除了 *const* 不允许你在变量创建后重新声明它。你仍然可以改变变量的属性，就像你可以用 *let* 一样。最佳实践是始终使用*常量*，除非您需要重新声明变量的值，然后使用 *let* 。

## 问:JavaScript 是一种单线程、同步编程语言，但也是异步的……这是怎么回事？

JavaScript 是单线程的，这意味着代码一次只能执行一条语句。这是因为 JavaScript 只有一个执行代码的调用堆栈，并且必须完成该代码的执行，直到进入下一个。堆栈顶部的代码(一个 [*堆栈*](https://www.geeksforgeeks.org/stack-data-structure/) 数据结构)将首先运行，直到堆栈为空。如果一段代码运行了很长时间，就说它阻塞了堆栈，阻止它继续运行下一段代码。阻塞堆栈将冻结页面的加载，直到代码完成并且堆栈继续运行。这赋予了 JavaScript 同步的特性。

JavaScript 也有异步能力，这是由运行它的浏览器中的引擎赋予的。使用像 fetch 这样的 Web APIs，或者最近的 [promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) ，我们可以在后台运行任务，而我们的调用栈仍然是一次执行一段代码。当一段异步(async)代码运行时，它实际上被发送到一个单独的容器，在那里它可以做一些工作(例如，一个获取数据的 HTTP 请求)，然后进入一个单独的回调队列(一个 [*队列*](https://www.geeksforgeeks.org/queue-data-structure/) 数据结构)，一旦所有的同步 JavaScript 都已运行，它将在那里等待进入调用堆栈。然后可以将数据加载到页面上。这可以防止代码工作时调用堆栈被阻塞。*进一步阅读，参见我的文章:*[*JavaScript 事件循环如何工作*](/what-is-the-javascript-event-loop-84d21ef276ee) *。*

## 问:函数声明和函数表达式有什么区别？

当声明一个 JavaScript 函数时，使用*函数*语法(类似于声明一个变量时如何使用 *const* )。在实际执行任何代码之前，函数声明在编译时被提升到代码的顶部。这允许在任何时候在代码中的任何地方调用函数声明；本质上，它是全球性的。

当我们使用表达式来构造函数时，就创建了函数表达式——如果函数在“=”的右边或者在“()”的内部。函数表达式是在运行时而不是编译时计算的，这意味着我们只有在它们运行时才能访问它们。因此，如果我们试图在函数在调用堆栈中运行之前调用函数表达式，我们将会得到一个错误。像回调这样的函数表达式允许我们在不必要的情况下，防止我们的全局作用域被过多的函数弄得混乱不堪。

## 问:*空*和*未定义*有什么区别？

Null 是不存在的值，必须赋值。它代表了有意义的价值的有意缺失。Undefined 表示变量已经声明，但尚未赋值。Undefined 的类型为 *undefined。* Null 有… *object 的类型？*没错！最初创建 JavaScript 时，一个错误导致 null 具有 object 类型，现在修复它会破坏太多东西。Null 仍被视为原始值。

只需看看这种疯狂的行为(来自 MDN):

```
typeof null          // "object" (not "null" for legacy reasons)
typeof undefined     // "undefined"
null === undefined   // false
null  == undefined   // true
null === null        // true
null == null         // true
!null                // true
isNaN(1 + null)      // false
isNaN(1 + undefined) // true
```

*更多内容尽在*[*plain English . io*](http://plainenglish.io/)