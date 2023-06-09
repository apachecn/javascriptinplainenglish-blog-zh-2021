# 这个网站不小心在源代码中留下了推广代码

> 原文：<https://javascript.plainenglish.io/this-website-accidentally-left-promo-codes-in-their-public-source-code-176c52fbfdc3?source=collection_archive---------1----------------------->

## 通过浏览网站找到有趣的东西

前段时间，[我曝光了一家网店](https://medium.com/dev-genius/are-14-people-currently-looking-at-this-product-e7fe8412f16b)公然谎报浏览其产品的人数。他们的公共源代码包含了一个 JavaScript 函数，这个函数将数字随机化。从那以后，网店的管理员已经悄悄地从他们的网站上删除了这段代码。

嗯，我们再次探索网站的源代码，但这一次没有涉及任何不正当的行为。我今天要给你看的网站只是在他们的公共代码中暴露了隐藏的推广代码。

我们今天将会看到一家名为“大灰狼小屋”的室内水上乐园连锁店，不过我想让你知道，网站通过糟糕的代码公开泄露内部信息实际上是很常见的。

我将解释这一过程中的每一步，这样您就可以按照我在本文中提到的方法探索其他网站的源代码。相信我，你可以在源代码中找到各种有趣的花絮。

这是我们要做的:

1.  我们将看一下《大灰狼》的源代码，在那里我们将找到推广代码的参考，我们将检查这些代码。
2.  我们将尝试网站上的促销代码之一，并抓取一个 web 服务器的 URL。
3.  剧透:最后，我们确实找到了一个有效的宣传代码。

## **探索源代码**

让我们开始导航到我们的主题:[大灰狼](https://www.greatwolf.com/poconos)。右键单击网站上的任意位置，然后选择“查看源代码”按 CTRL+F(或 CMD+F)搜索代码并键入“promocode”我们将发现两个特别令我感兴趣的变量:“dealPromoCodeApiUrl”和“promoCodeList”。第一个变量包含一个 JSON 文件(一个带有结构化数据的文件)的部分 URL，听起来像是包含促销代码。第二个变量是促销代码的数组(集合)。

如果我们获取在上述变量中找到的 URL，并在它的开头添加“greatwolf.com”，我们将得到这个 URL:[https://www . great wolf . com/content/experience-fragments/gwl/poco nos/experience-fragment/master/_ JCR _ content/root/plan . JSON](https://www.greatwolf.com/content/experience-fragments/gwl/poconos/experience-fragment/master/_jcr_content/root/plan.json)。

在撰写本文时，在访问该网址时，我收到了四个不同的促销代码:

![](img/625a2602fd9638764a10d40820ec092c.png)

Data found on [Great Wolf](https://www.greatwolf.com/content/experience-fragments/gwl/poconos/experience-fragment/master/_jcr_content/root/plan.json). Screenshot by the author.

如果您在浏览器中访问该 URL，数据可能不会像我看到的那样结构化。有些浏览器有内置的 JSON-viewer，但大多数没有。然而，每个主要的桌面浏览器都有你可以安装的扩展来美化 JSON-files，所以你可以简单地访问你的浏览器的扩展/应用商店，搜索 JSON 来找到一个。

无论如何，让我们记住这些代码，但让我们也检查一下我们之前发现的另一个变量:“promoCodeList”通过查看源代码，我们已经知道了它的内容，但是我们可以在浏览器的控制台中更容易地查看它。让我们打开我们的浏览器开发工具，你可以在 Windows PC 上的大多数浏览器中按 F12 键。在大多数电脑和浏览器上，你也可以在网站的任何地方点击右键，选择类似于“检查元素”的东西打开我们的开发工具后，我们需要选择“控制台”最后，我们可以键入“promoCodeList”并按回车键，我们将看到另外五个促销代码:

![](img/9ee4575f20bcd9f73c40997a3bdc0782.png)

Data found on [Great Wolf](https://www.greatwolf.com/poconos). Screenshot by the author.

让我们试试这些中的一个。在灰太狼的主页上，有一个选项可以搜索靠近屏幕顶部的可用日期。我将搜索一些日期，选择一位客人，并输入我之前发现的促销代码:PROMO20。

![](img/251628896f4044adc31052ee4fea49d9.png)

Screenshot from [Great Wolf](https://www.greatwolf.com/poconos) by the author.

搜索完成后，我收到一条短信:“很遗憾，这不是有效的优惠代码。请重新输入或查看我们的其他优惠。”

## 与 Web 服务器对话

我总是很好奇数据是如何在网站和网络服务器之间来回传送的，所以让我们来看看我们的开发者工具的网络标签。选择“XHR”以查看网页和 web 服务器之间传输的数据。如果标签为空，请刷新网页。网络选项卡现在充满了 API 调用。如果你不知道 XHR 和 API 这样的缩写是什么意思，不用担心；它们基本上意味着网站正在与服务器对话。

![](img/c25736385a14aff6acaa8048834b66b9.png)

Network calls made on [Great Wolf](https://www.greatwolf.com/poconos) when searching for a suite. Screenshot by the author.

其中大多数听起来并不有趣，但是突出显示的一行引起了我的注意。它写着“可用性”，看起来像是在发送有趣的数据。如果我点击它，我的浏览器将显示一个 URL，网站使用它向服务器请求可用的套件。

![](img/4f558e52c769a5d2b2129c930ece06ff.png)

Network calls made on [Great Wolf](https://www.greatwolf.com/poconos) when searching for a suite. Screenshot by the author.

如果你在写作的时候点击[这个网络标签中显示的网址](https://gwrapiprod-azure.greatwolf.com/availability/api/v2.2/Availability?arrival=2021-04-05%2000:00:00&departure=2021-04-07%2000:00:00&location=POCOPA&numberOfAdults=1&offerCode=PROMO20&kidsAges=&uuid=44f4af34-63d2-4d20-80f9-396b7457f107&intUserId=3de681e2ba74f3a8)，你将会进入另一个充满数据的页面。此页面上的结果包含我们所选日期可用的套房。方便的是，在数据的顶部是关于促销代码的信息。有一个错误代码表示该提议无效(我们已经知道了)。

![](img/96912dfd7d98577c53b811250b3a4d4a.png)

Data found on [Great Wolf](https://gwrapiprod-azure.greatwolf.com/availability/api/v2.2/Availability?arrival=2021-04-05%2000:00:00&departure=2021-04-07%2000:00:00&location=POCOPA&numberOfAdults=1&offerCode=PROMO20&kidsAges=&uuid=44f4af34-63d2-4d20-80f9-396b7457f107&intUserId=3de681e2ba74f3a8). Screenshot by the author.

可悲的是，这些数据并不太有趣，但这个网址让我更容易尝试其他促销代码。你看，如果你看看网址，你会发现一个位说“优惠代码=促销 20。”我可以在这里输入一个不同的促销代码，然后重新加载 URL 来试用。不久，我就成功了。我之前找到的一个宣传语代码很管用:“FLING40。”在写这篇文章的时候，如果你点击[这里](https://gwrapiprod-azure.greatwolf.com/availability/api/v2.2/Availability?arrival=2021-05-04%2000:00:00&departure=2021-05-07%2000:00:00&location=POCOPA&numberOfAdults=1&offerCode=FLING40&kidsAges=&uuid=c3f4115b-4914-420d-bfaf-e897770800bf&intUserId=9e590e65c9d83d5d)，你会收到这样的回复:

![](img/973b319c752b9ad4aa4a8959f96dbb2c.png)

Data found on [Great Wolf](https://gwrapiprod-azure.greatwolf.com/availability/api/v2.2/Availability?arrival=2021-05-04%2000:00:00&departure=2021-05-07%2000:00:00&location=POCOPA&numberOfAdults=1&offerCode=FLING40&kidsAges=&uuid=c3f4115b-4914-420d-bfaf-e897770800bf&intUserId=9e590e65c9d83d5d). Screenshot by the author.

事实上，如果我回到网站并输入促销代码，我可以看到它正确适用:

![](img/39ec1e887d4678e88e2aaacef0dd93f2.png)

Screenshot from [Great Wolf](https://www.greatwolf.com/poconos) by the author.

任务成功。

我还应该提到的是，我们之前发现的一些促销代码在[灰太狼的“交易”——第](https://www.greatwolf.com/poconos/deals)页上一览无遗。然而，我们最终使用的代码 FLING40 不在那里。

## 概括起来

我们通过一些非常简单的技术[发现了一个预订网站的促销代码](https://www.dontpayfull.com)。我们查看了源代码，发现了一些有趣的 JavaScript 变量。我们检查了一下，发现了一些隐藏的促销代码。我们还找到了一个 URL，可以与 Great Wolf 的 web 服务器进行对话，以便更快地测试代码。最后，我们发现了一个隐藏的促销代码，它起作用了。

你可能想知道为什么推广代码只是躺在公共源代码的一些随机变量中。可能有很多原因，但根据我自己作为开发人员的经验，我认为通常是因为管理问题。紧张的截止日期、缺乏严格的测试阶段、范围的后期增加或者写得不好的需求表都可能是这样暴露数据的原因。

此外，由于数据是良性的，也可能没有理由删除它。这是一个无意识的错误，比人们想象的要普遍得多。当然，我不得不提到，留下代码也可能是有意为之，作为一个天才的伎俩来获得曝光或推动销售。但我真的很难相信。

无论如何，我希望您学到了一些新东西，并乐于在其他源代码中寻找好东西。

*感谢阅读！如果你喜欢这篇文章，你可能也会喜欢这两段文字:*

[](/this-recruitment-website-publicly-exposes-user-data-6a2f5736f805) [## 这个招聘网站公开暴露用户数据

### 我发现超过 1000 个用户的工资期望值

javascript.plainenglish.io](/this-recruitment-website-publicly-exposes-user-data-6a2f5736f805) [](https://medium.com/dev-genius/are-14-people-currently-looking-at-this-product-e7fe8412f16b) [## 一个网上商店的源代码中揭露的无耻谎言

### 14 个人真的在看这个产品吗？

medium.com](https://medium.com/dev-genius/are-14-people-currently-looking-at-this-product-e7fe8412f16b)