# 如何在 JavaScript 中实现链表

> 原文：<https://javascript.plainenglish.io/how-to-implement-a-linked-list-in-javascript-8dd148a1755d?source=collection_archive---------9----------------------->

![](img/1fbc62059f00e8b4697c0cc125247253.png)

Photo by [John Matychuk](https://unsplash.com/@john_matychuk?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/s/photos/train-snow?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

北极很冷。我不明白为什么圣诞老人坚持在那里度过一年的大部分时间。但事实如此，我们必须面对它。问题不缺。在名牌被今天的大雪损坏后，又发生了一起事故。有人忘了检查礼物列车车厢的修订日期。显然，火车晚点了。

# 难题:列车维护🚂

![](img/ac59a01b9ea072cd67d06543914f7c5b.png)

[开发降临节日历的第 10 天🎅我绝对已经走出了我的舒适区。今天的问题涉及链表。根据维基百科的说法，它们是基本的动态数据结构。我不得不承认我以前从未用过它们。](https://github.com/devadvent/puzzle-10)

第一件事是了解它们是什么。网上有很多文章，有些比其他的更专业。维基百科是一个很好的开始。但我也发现三个具体的帖子很有帮助。首先是对各种类型的链表的概述。还有一些 C ++和 Python 的样本代码。

[](https://www.freecodecamp.org/news/data-structures-explained-with-examples-linked-list/) [## 数据结构举例说明——链表

### 就像花环是用花做的一样，链表是由节点组成的。我们称这种特殊的花为…

www.freecodecamp.org](https://www.freecodecamp.org/news/data-structures-explained-with-examples-linked-list/) 

另外两个涉及用 JavaScript 实现链表。它们有助于我大致了解如何处理今天的难题。

[](https://www.freecodecamp.org/news/implementing-a-linked-list-in-javascript/) [## 如何在 JavaScript 中实现链表

### 如果你正在学习数据结构，链表是你应该知道的一种数据结构。如果你真的不…

www.freecodecamp.org](https://www.freecodecamp.org/news/implementing-a-linked-list-in-javascript/) [](https://medium.com/swlh/singly-linked-list-in-javascript-a0e58d045561) [## JavaScript 中的单链表

### 链表和数组一样，是一种线性数据结构。它包含头部、尾部和长度属性。如下图所示…

medium.com](https://medium.com/swlh/singly-linked-list-in-javascript-a0e58d045561) 

YouTube 上没有很多解释它们是什么的快速视频。有一些视频，做得很好，但是很长。幸运的是 [Anthony Sistilli](https://www.youtube.com/channel/UCoYzQqZNCRqqAomJwJ6yEdg) 在 3 分钟内总结了基本概念:

简而言之，链表是对象的集合，每个对象都是前一个对象的属性。

![](img/39b800c429fbf41e3ae7ba3f1e000d39.png)

它们是这样制作的:

根本属性是`next`。实际上，我们可以随意称呼它，但是`next`是一个非常明确的术语。`mario`对象是列表中的`head`。所有元素都是结构的`nodes`。

我可以这样重写前面的代码:

我也可以创建更长更复杂的结构，但我认为这足以理解基本概念。

# 迭代列表中的元素

这个问题要求你仔细检查一系列项目，并对每一项采取行动。强行比较就是创造一种`map()`的方法。

第一步是理解如何在所有不同的元素之间迭代。在这种情况下，使用这种结构，最好使用一个 [while](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while) 循环:只要属性本身存在，我就滚动每个元素的下一个属性:

这段代码是我构建解决方案的基础。怀疑也将是链接到链表的所有其他方法的基础。

# 过滤链接列表中的项目

为了让这个列表有用，也为了解决这个难题，我需要给`iterateList`函数添加几个参数。我补充一下`actionFn`的说法

我还需要一种方法，只对列表中的某些项目执行操作。一种过滤器，`filterFn`:

这就是我解决问题所需要的。我的解决方案的完整代码，在重命名变量以便于阅读之后，是这样的:

解决这个问题后，我花了一些时间试验链表。我整理了一份清单，列出了一些可能对我未来有用的方法。我把它们带回来，为了未来的我。

# 计算链表的大小

第一种方法允许计算列表中存在的节点数量。

但是我也可以从`iterateList()`开始得到同样的结果:

# 计算链表中满足条件的节点数

我更喜欢第二种方法，因为您可以很容易地修改它来计算列表中满足给定条件的节点数:

# 查找链表中的最后一个节点

在数组中，很容易找到最后一个元素。对于链表，您需要滚动所有节点，直到到达最后一个节点:

我可以添加一个过滤器来获取满足给定条件的最后一个节点:

# 根据条件查找列表中的第一项

我可以修改最后一个函数来创建一个方法，以获得满足特定条件的第一个节点:

# 根据节点的位置在链表中查找节点

虽然没有索引，但和数组一样，可以根据位置获取链表的节点。

我也可以决定从`1`开始计数元素，而不是从`0`开始计数:只需改变`counter`的初始值。

# 在链表的开头添加一个节点

到目前为止，我只在各种节点中进行了搜索。但是添加一个新节点会很有用。最简单的情况是当我们想要在开头添加一些东西时，模仿数组的`unshift()`方法:

事情变得有点复杂。此时，建议创建一个特定的类来管理各种边界情况。我推荐阅读我在开头链接的由[古尔吉娜·阿金](https://medium.com/u/78a7e5dcef6a?source=post_page-----8dd148a1755d--------------------------------)写的帖子。

# 删除列表顶部的节点

删除列表头很快:

# 在列表末尾添加一个节点

向列表末尾添加一个节点需要额外的步骤。我必须首先找到最后一个节点，然后将新节点添加到该节点:

在一行中，它将是:

# 删除列表末尾的节点

以对称的方式，我可以删除链表的最后一个元素:

或者以一种更为综合的方式

# 在链接列表中添加项目

另一个有用的操作是在列表的特定位置插入一个元素。为此，我必须更改所需位置之前的元素。

# 从列表中删除节点

删除节点包括修改它前面的节点。

# 编辑节点

剩下的最后一个常见操作是修改节点。这种情况非常简单，只需用`getByIndex()`检索要修改的节点

今天到此为止。感谢阅读！敬请关注更多内容。

***不要错过我的下一篇文章—报名我的*** [***中邮箱列表***](https://medium.com/subscribe/@el3um4s)

[](https://el3um4s.medium.com/membership) [## 通过我的推荐链接加入 Medium—Samuele

### 阅读萨缪尔的每一个故事(以及媒体上成千上万的其他作家)。不是中等会员？在这里加入一块…

el3um4s.medium.com](https://el3um4s.medium.com/membership) 

*更多内容看* [***说白了就是***](http://plainenglish.io/) ***。*** *报名参加我们的* [***免费每周简讯这里***](http://newsletter.plainenglish.io/) ***。***