# 提高网站可访问性的 6 个有用技巧

> 原文：<https://javascript.plainenglish.io/6-useful-tips-to-improve-your-websites-accessibility-d47dd446d82?source=collection_archive---------14----------------------->

## 可达性可能比你想象的更重要，尤其是在 2021 年。

![](img/cb09298ab9ce836086770172dd3368f5.png)

Photo by [Luke Peters](https://unsplash.com/@lukepeters?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

大多数时候，你需要确保每个人都可以访问你的网站。许多使用网络的人有各种障碍，也许他们甚至看不见，他们只使用屏幕阅读器。

这就是可访问性发挥作用的地方，以确保每个人都可以轻松地使用网络，无论他们有什么障碍。因此，如果你想提高转换率，降低跳出率，你需要始终关注让每个人都能访问你的网站或网络应用。更重要的是，这些有障碍的用户也有权轻松访问网络。

你可以做很多事情来提高你的网站或应用程序的可访问性。这就是为什么在这篇文章中，我会给你一些作为开发者或网站所有者需要考虑的易访问性提示。所以让我们开始吧。

# 1.语义 HTML

编写语义 HTML 是拥有一个每个用户都能轻松使用的可访问网站的第一步。

当我说语义 HTML 时，我指的是使用语义标签，如`header`、`nav`、`main`、`article`、`aside`、`footer`等等。像`div`和`span`这样的标签或元素是没有语义的，你应该只把它们用于布局目的。

对于有视觉障碍的人来说，语义 HTML 在屏幕阅读器方面非常有用。例如，如果你想创建一个按钮，确保使用标签`button`，而不是`div`或`a`。因此，这将让有视觉障碍的人知道有一个他们需要点击的按钮。

因此，始终使用语义 HTML，以便屏幕阅读器可以检测到您网站上的元素，并告诉残疾用户他们需要采取什么行动。

# 2.响应式设计

让你的网站或应用程序完全响应是非常重要的。现在是 2021 年，借助媒体查询、CSS Grid 和 Flexbox 的强大功能，一切都变得更加容易。

因此，一定要确保你的网站针对所有屏幕和设备进行了优化。它应该在手机、平板电脑和 PC 屏幕上看起来不错。因此，所有使用不同类型设备的用户都可以访问您的网站或应用程序。

# 3.小心使用颜色

有很多人有视觉问题，他们看不太清楚。当您使用对比度较低的颜色时，有视觉障碍的人可能很难阅读您网站上的内容。

你需要确保你使用的颜色有很高的对比度，让人们可以很容易地浏览和使用你网站上的内容。这对于可访问性非常重要。

# 4.允许调整大小并为文本使用合适的字体

说到文本，你需要注意让它具有可读性，这样用户才会有好的体验。

尽量使用清晰易读的字体。只是一个不会打扰用户的字体。除此之外，请确保为文本设置了合适的字体大小，并使其可调整大小。

为什么可调整大小？大多数浏览器和服务允许用户调整字体大小，以便他们可以轻松阅读和访问内容。这非常有用，尤其是对于有视觉障碍的人。因此，如果你想让这些用户在不破坏网站设计的情况下轻松调整文本大小，确保使用相对单位，如`rem`或`em`作为字体大小。

# 5.对图像使用 alt 属性

为了提高可访问性，你可以做的一件非常重要的事情就是确保你为你网站上的所有图片添加了替换文字。

HTML 中的属性`alt`允许您编写描述图像的文本。这对有视觉障碍的人非常有用，因为他们看不到图像。当图像由于某种原因无法加载时，这也很有用，这样至少用户会知道图像是关于什么的。

# 6.为表单使用标签

通常，一个表单至少包含一个以上的输入元素。同样，许多用户有视觉障碍。所以他们需要知道每个表单输入字段的用途。是邮件字段吗？用户名字段？谁知道呢？

因为这些用户使用屏幕阅读器，所以您需要使用表单标签，以便屏幕阅读器知道每个输入字段的用途并告诉用户。所以在 HTML 表单中总是使用元素`label`。

这里有一个例子:

```
**<label for="email">Email:</label>**
<input type="email" name="email" id="email">
```

如果你想隐藏标签，你也可以使用属性`aria-label`来描述表单输入。

这里有一个例子:

```
<input type="text" name="search" **aria-label="search"**>
```

# 结论

正如你在上面的列表中看到的，这些是你需要考虑的简单重要的提示，让你的网站或应用程序对每个人都是可访问的。可访问性对你和用户都有很多好处。它可以让你的网站更容易使用，提高转化率，降低跳出率，等等。

感谢您阅读这篇文章。希望你觉得有用。

**更多阅读:**

[](/5-simple-ways-to-fetch-data-in-react-e72db174c71a) [## 在 React 中获取数据的 5 种简单方法

### 用实例反应数据获取。

javascript.plainenglish.io](/5-simple-ways-to-fetch-data-in-react-e72db174c71a) [](/10-awesome-front-end-development-tools-to-boost-your-productivity-b1d2efc4c4ba) [## 10 个令人敬畏的前端开发工具来提高您的生产力

### 你可能需要用到的有用的前端开发工具。

javascript.plainenglish.io](/10-awesome-front-end-development-tools-to-boost-your-productivity-b1d2efc4c4ba) 

*更多内容看*[***plain English . io***](http://plainenglish.io/)