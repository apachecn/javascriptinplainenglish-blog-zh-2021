# Gatsby vs. Next.js:静态网站生成大战

> 原文：<https://javascript.plainenglish.io/gatsby-vs-nextjs-static-site-generation-shootout-65198d80e1c?source=collection_archive---------6----------------------->

![](img/fcb327fd6f7c792b8b21de09086172a5.png)

Photo by [Hermes Rivera](https://unsplash.com/@hermez777?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

尽管有疫情，2020 年对 Next.js 来说是重要的一年。他们发布了静态站点生成(SSG)支持，增加了预览模式，甚至内置了语法上令人敬畏的样式表(SASS)支持。除了其功能，Next.js 现在是最灵活的前端框架，并且由于构建在 React 上，编写代码很容易。你可以使用 JSX，钩子和大量的模块库。

但是一个难以回答的问题仍然困扰着我:在目前阶段，这是静态站点生成的最佳选择吗？从一个不同的平台转换并采用它值得冒险吗？前端开发领域的前景如何？我想弄清楚。

[**盖茨比**](https://www.gatsbyjs.com/) **和** [**下一个**](https://nextjs.org/) **是眼下 SSG 最让人兴奋的两个名字。它们都是基于反应的。他们都有很大的社区。但是你应该选择哪一个呢？**

# 什么是静态站点生成？

大多数程序员应该熟悉静态站点的概念。自从在网络服务器上建立简单的网站以来，这个概念又回到了起点。它们不会主动连接到数据库，也无法在用户执行操作时更新最新内容。根据请求，所有信息都被加载到用户的浏览器中。您可以对已经加载到浏览器中的信息执行操作，处理路由，隐藏和显示信息。

**与过去的静态网站不同，这些网站现在可以通过一个钩子来触发重建。每次站点重新构建时，您可以调用内容管理系统并获取相关信息来填充页面。**

相比之下，动态网站允许用户交互，并可以基于这种交互显示不同的信息。动态网站最适合涉及计算、大量 UI 元素的应用程序，并且交付数据的时间很重要。在当今时代，我们接触的大多数网站都是动态网站。它们连接到一个 API 来获取数据、处理状态和动态更新。Spotify for desktop 只是一个包裹在[电子](https://www.electronjs.org/)中的动态 javascript 网站。

动态网站的托管成本很高，而且由于其设计的连接性，可能会带来安全风险。如果可能的话，出于简单、可维护性和成本的考虑，创建一个 SSG 网站总是一个更好的主意。您甚至可以更进一步，合并无服务器函数(lambda 函数),它可以处理类似 SSG 网站上的“联系我”表单之类的事情，而不需要创建服务器来处理这种数据提交。

# 类似

不可能逃避事实:这些技术都是 javascript、react、基于节点的框架。就像人类的金鱼一样，它们拥有惊人数量的 DNA。虽然不同平台之间的范例略有不同(Gatsby 包含了更多的“魔法”)，但组件编程在很大程度上是相同的。

我喜欢 typescript，这是一种 javascript 类型安全语言。然而，与 Angular 不同，Gatsby 和 Next 都不支持它。事实上，虽然很容易就可以将 Gatsby 转换成 typescript，但是为了让应用程序工作，您至少需要有`gatsby-config.js`，尽管您可以使用一个包将所有其他 Gatsby-ism 转换成 typescript。另一方面，Next 能够完全转换成 typescript，这有助于减轻我在编程时对组织的需求。

从这张对比图中可以看出，《盖茨比》在 npm 上的下载量还不到一半。然而，我认为这说明了一个事实，即 Next.js 更加通用，并且已经成为一个流行的客户端和服务器端框架。

# 盖茨比（姓）

![](img/487a4fdcf4595b33efb517e944c9b7cb.png)

## 赞成

Gatsby 于 2015 年首次推出，已成为快速、资源密集型网站静态托管的最佳方式。它附带了一个很棒的插件库，允许你获取数据，处理图像和图标，提供离线支持，轻松添加打字支持，谷歌分析，等等。简单地`npm install`这个包并把它添加到你的`gatsby-config`文件中。以最小的努力获得几乎无限的可能性。无论你是想创建一个投资组合网站、博客还是电子商务商店。

除了这些过多的社区和 Gatsby 制作的插件，Gatsby 背后还有一个相当大的社区，它长期以来一直专注于静态站点生成。对特定问题的支持或对您选择的无头 CMS 的支持只需点击鼠标即可完成。这意味着您需要花费更少的前期时间与公共服务进行交互。

此外，大多数平台即服务(PaaS)提供商都有设置 Gatsby 项目的文档。事实上，[盖茨比云](https://www.gatsbyjs.com/cloud/)甚至是托管你的新应用的一个选项。因为生产中的 Gatsby 是纯静态的，所以它可以在没有服务器的情况下运行，这可以大大节省服务器成本。

## 欺骗

盖茨比固执己见，你最好喜欢用 GraphQL。虽然我认为 GraphQL 是不可思议的，*不要告诉我该做什么*。Gatsby 是围绕 GraphQL 是数据源的核心这一概念构建的，虽然您可以添加不同的数据源，如 gatsby-source-rest-api，但这偏离了处方。

在 SSG 之外，盖茨比作为一个平台缺乏灵活性。因为它纯粹是 SSG 的焦点，你需要确定你的网站是否会使用动态功能。虽然无服务器功能可以在一定程度上弥合这一差距，但您最好确定您的应用程序的未来。为了添加健壮的动态功能，您需要使用一个过时的解决方案，比如使用 iframes。

# 然后

![](img/2fd97a42da4e2d75d4b199e8bc83b30a.png)

## 赞成

最近，SASS 成为该平台的标准。虽然用普通 CSS 编程仍然是可能的，但这并不意味着 Next 现在是自以为是的了。我认为在这种情况下，捆绑 SASS 是一个很强的举措，除了那些喜欢替代 CSS 预处理程序如 Emotion 的人之外，很少有人会改变它。

Next 最近也开始增加一些功能来与 Gatsby 竞争，比如一种预览模式，这种模式实际上更容易管理，可以在 express 上运行。此外，它们还有`<Image />`，可以让你优化图像，类似于常见的“模糊”和“svg 绘制”功能。这确保了即使一些图像可能需要更长的加载时间，也有一个合适的占位符可以在完整图像加载时接近即时。

此外，也许是最重要的，为了从 Next.js 中获得最大的效果，它需要成为生成和提供静态页面的服务器。虽然它也提供了像 Gatsby 的方法一样的导出能力，但这是一个强大的功能，允许您创建混合体验。静态和动态站点可以位于同一台服务器上。

## 欺骗

Next 作为一个框架，总的来说是在 2016 年推出的。2020 年增加了静态站点生成。相比之下，与盖茨比相比，Next 还处于起步阶段。

虽然 Next.js 有一个庞大的社区和大量的下载，但它的进展分成三个阵营:静态站点生成、客户端渲染和它最出名的:服务器端生成。

对于开发者来说，最大的问题可能是成本:托管一个服务器比托管一个无服务器的模型成本更高。虽然可以导出一个完全静态的 Next.js 项目，但是您会失去它提供的一些更好的特性。Next.js 只是更喜欢自己构建和服务。这是有代价的。

# 裁决

您的里程可能会有所不同，但在一个需要考虑未来和未来的项目中，选择一个能够经得起快速发展的技术团队使用和滥用的框架是最好的选择。在渲染方面，我没有那么固执己见，也没有太多选择，我发现 Next 是最明显的赢家。虽然 Next 的用户群分为静态网站生成、客户端和服务器端渲染，但我们看到 SSG 部分令人兴奋的增加。随着用户数量的翻倍，我预测下一个 SSG 将很快被主机提供商、CMS 提供商和教程网站广泛采用。

虽然 Gatsby 提供了大量的文档、社区、插件和来自各种提供商的支持，但它的灵活性较差，这意味着它的受众有限。虽然我不想比较非 SSG 的功能，但我忍不住把它们视为 Next 的有利资产。我不认为盖茨比会消失，但我确实认为 Next 将会成为 SSG 的首要框架。

我的警告是，如果开发的速度和成本对你来说很重要:Gatsby 有更多的插件和现有的支持，可以让你快速启动并运行。对于小型和个人项目，Gatsby 是一个非常好的选择，可以非常快速地构建和模板化博客、投资组合网站、小公司虚荣网站和其他类似的产品。对于拥有跨职能团队的更成熟的产品来说，Next 是最好的选择。