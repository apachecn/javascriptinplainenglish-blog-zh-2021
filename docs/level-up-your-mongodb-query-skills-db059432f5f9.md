# 提升您的 MongoDb 查询技能

> 原文：<https://javascript.plainenglish.io/level-up-your-mongodb-query-skills-db059432f5f9?source=collection_archive---------9----------------------->

## 主 MongoDb 查询

![](img/d3896813b54e78bf5056ecedcde7c9c5.png)

Photo by [Filip Mroz](https://unsplash.com/@mroz?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/s/photos/stairs?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

每个 web 开发人员都喜欢 MongoDB。好吧，好吧，几乎每个网络开发者。它是市场领先的基于文档的数据库平台绝非偶然。MongoDB 非常灵活，允许开发人员快速存储大量非结构化数据。

在本指南中，我们将学习如何编写 MongoDB 查询，例如:

CRUD 操作:

*   创建(`insertOne()`，`insertMany()`)
*   读(`findOne()`，`find()`)
*   更新(`updateOne()`，`update()`)
*   删除(`deleteOne()`，`deleteMany()`)

更高级的查询操作使用:

*   读取选项(`sort`、`limit`、`skip`、`projection`)
*   比较查询运算符(`$gt`、`$lt`、`$gte`、`$lte`)
*   设置运算符(`$in`、`$all`、`$nin`)
*   布尔运算符(`$ne`、`$not`、`$or`、`$nor`、`$exists`)

我将使用 Node.js 驱动程序连接到 MongoDB。你可以在这里看到如何连接到你喜欢的语言的驱动程序。

MongoDB connection

成功连接到 MongoDB 之后，让我们继续查看各种 MongoDB 查询。

**创建操作**

创建或插入操作向集合中添加新文档。以下方法可用于将文档插入集合:

*   **insertOne:** 将单个文档插入集合。
*   **插入多个**:将多个文档插入一个集合。

让我们看看这些方法的用法:

首先，我们将创建一个用户集合，在其中插入文档，使用 insertOne 插入单个文档，使用 insertMany 插入一个文档数组。

根据这个查询，`insertOne()`将把单个文档`user`插入到用户集合中，而`insertMany()`将把多个文档`multipleUsers`插入到用户集合中。

**读取操作**

您可以使用读操作从 MongoDB 数据库中检索数据。要从集合中检索文档，可以使用以下方法之一:

*   **find** :在您想要查询的集合上调用这个方法。要检索集合中的所有文档，将一个空文档作为查询过滤器参数传递给`find()`。为了检索特定的文档，`find()`接受一个描述您想要选择的文档的查询文档。
*   **findOne:** 这个方法用于从集合中检索单个文档。您需要为该方法提供一个查询参数，它将使用该参数返回集合中与查询匹配的文档。`findOne()`只返回第一个匹配的文档。如果不提供查询文档，或者提供一个空文档，MongDB 将匹配集合中的所有文档。

Retrieve documents using find and findOne

第一个查询将返回`User`集合中的所有用户，第二个查询将返回`firstName`字段值为`Chinedu`的所有用户，第三个查询将只返回一个文档，其中`firstName` 字段值为`Lebron` ，而`lastName` 字段值为`James`。

**更新操作**

MongoDB 中的更新操作修改集合中的现有文档。让我们来看一下更新方法:

*   **updateOne** :该方法用于更新单个文档。`updateOne()`接受过滤文件和更新文件。如果查询匹配集合中的文档，`updateOne()`将使用更新文档更新文档的相关字段。如果没有与您的过滤器匹配的文档，您可以将`upsert`选项设置为真，以创建一个新文档。

请考虑以下情况:

这个查询将首先检查集合中是否有用户的`firstName`是`Chinedu`。如果找到一个以上的用户，第一个匹配过滤器的文档将用一个`hobbies`字段和一个数组值进行更新，但是如果没有找到用户，则不会更新任何文档。

*   **updateMany:** 该方法用于更新多个文档。`UpdateMany()`接受过滤文档和更新文档。如果集合中的任何文档与过滤器匹配，它将被更新文档替换。

请考虑以下情况:

该查询将匹配所有的用户，其中`firstName`字段值为`Cristiano`，并且将他们的年龄增加 1。

**删除操作**

`deleteOne()`和`deleteMany()`方法用于从集合中移除文档。让我们看看这些方法是如何工作的:

*   **deleteOne:** 该方法用于删除集合中的单个文档。`deleteOne()`接受查询文档并删除第一个匹配的文档。如果您没有提供查询文档，或者如果您提供了一个空文档，MongoDB 将匹配集合中的所有文档并删除第一个匹配。

请考虑以下情况:

该查询将匹配`User`集合中第一个文档，其中`firstName`字段值为`Chinedu`，并删除它。

*   **deleteMany:** 该方法用于删除集合中的多个文档。`deleteMany()`接受查询文档并删除集合中所有匹配的文档。如果您没有提供查询文档，或者如果您提供了一个空文档，MongoDB 将匹配集合中的所有文档并删除它们。

请考虑以下情况:

该查询将选择并删除`User`集合中`lastName`字段值为`James`的所有文档。

**MongoDB 查询 Max**

本节是对 MongoDB 查询功能的更全面的参考。

**跳过、限制和排序查询选项**

*   **Skip:** 查询集合时，`skip()`用于控制 MongoDB 从哪里开始返回结果。这通常用于实现分页结果。
*   **Limit:** 该方法用于指定将被返回的文档的最大数量。这种方法类似于 SQL 数据库中的`LIMIT`语句。这很有用，因为它将防止 MongoDB 返回不需要的结果，从而最大化性能。
*   **排序:**该方法指定查询返回匹配文档的顺序。如果您想以升序或降序返回匹配的文档，这个方法将帮助您实现这一点。

让我们来看看它们的用法:

该查询将返回前三个用户，按年龄升序排列。

**投影**

Projection 用于指定要从查询结果中的每个文档返回或传递到管道下一阶段的字段。

假设您想检查数据库中是否存在一个用户:

如果用户存在，将返回整个文档，但是您不希望仅仅为了检查用户是否存在而返回整个文档。您可以使用投影来限制返回的字段。

要进行投影，您需要为`find()`或`findOne()`查询提供一个额外的参数。此参数包含 include 或 exclude 规范。将想要返回的字段的值设置为 1，将想要排除的字段的值设置为 0。

考虑下面的例子:

如果这个用户存在，将只返回`_id`字段。

注意，除非`_id`字段被明确排除，即`_id: 0`，否则默认情况下它总是被包含在内。

如果该用户存在，将返回`lastName` 和`_id`字段，因为默认包含`_id`字段。

在某些情况下，您可能希望指定要排除的字段。例如，如果我们想返回没有年龄的用户，我们在 projection 参数中将年龄值设置为零:

该查询将返回除年龄之外的所有用户字段。

**比较查询运算符**

大多数情况下，您会希望查询某个范围内的文档。在大多数编程语言中，这可以通过`<`、`<=`、`>`和`>=`符号来实现。对于 MongoDB，使用`$lt`、`$lte`、`$gt`和`$gte`组操作符来实现这一点。让我们分别来看看:

*   **$lt:** lt 是小于的缩写，`$lt`操作符选择字段值小于指定值的文档。

考虑一下这个:

该查询将选择并返回所有 39 岁以下的用户。

`$lt`操作符也可用于嵌入文档。假设我们的用户集合中有一个嵌入式文档，比如地址字段中有一个邮政编码:

我们可以使用`$lt` 操作符，通过以下查询来查找住在拉各斯维多利亚岛的用户:

我使用了一个我们还没有讨论过的操作符`$gt`，但是这个查询检索邮政编码大于`101240`小于`101242`的用户，基本上是居住在维多利亚岛的用户(`101241`)。

*   我知道你已经猜到了，gt 代表“大于”`$gt` 匹配字段值大于指定值的文档。

请考虑以下情况:

该查询查找 39 岁以上的用户。与`$lt`一样，`$gt` 运算符也可以用在嵌入式文档上。

*   **$lte:** `$lte` 选择字段值小于或等于指定值的文档。该运算符的使用方式与`$lt` 的使用方式相同:

此查询选择小于或等于 17 岁的用户。

*   **$gte:** `$gte` 选择字段值大于或等于指定值的文档。

请考虑以下情况:

该查询选择 18 岁及以上的用户。

组合这些运算符时，不要犯重复搜索字段的常见错误:

上面的查询只考虑了最后一个条件。正确表达查询:

请注意，只有当值属于同一类型时，范围查询才会匹配这些值。也就是说，在一个文档集合中，如果您有一个字段的值由多种类型组成(例如，数字和字符串)，并且您发出一个范围查询，比如说`{field: {$lt: 100}}`，该查询将只匹配和检索字段值为数字的文档。如果需要字符串结果，则必须用字符串进行查询。

**设置操作符**

集合运算符包括`$in`、`$nin`和`$all`。这些查询运算符将一个或多个值的列表作为筛选条件。让我们分别来看看:

*   **$in:** 如果任何给定值与搜索字段匹配，该操作符将返回一个文档。如果该字段包含一个数组，`$in`操作符将返回集合中至少有一个给定值与搜索字段匹配的所有文档。

请考虑以下情况:

这个查询基本上是说，找到 39 岁或 40 岁的用户。从我们的用户集合中，我们只有一个 39 岁的用户(Serena Williams ),没有 40 岁的用户。因此，将返回一个文档。

*   **$nin:** `$nin` (not in)仅当给定元素都不匹配搜索字段时，才返回文档。从用户集合中，我们可以使用这个操作符来查找既不是 18 岁也不是 50 岁的用户:

该查询将返回用户集合中年龄字段值既不是 18 也不是 50 的所有文档。没有一个用户的年龄在 18 岁或 50 岁，因此，将返回用户集合中的所有文档。

*   **$all:** `$all`如果所有给定元素都匹配搜索关键字，则匹配。我们可以利用`$all`操作符来查找爱好字段值包含`Football`和`Chess`的用户:

该查询将只返回爱好字段包含足球和象棋的所有用户。

**布尔运算符**

MongoDB 的布尔运算符包括`$ne`、`$not`、`$or`、`$and`、`$nor`和`$exists`。

让我们来了解一下他们:

*   **$ne:** 比方说由于某种原因，你想检索除了 45 岁以外的所有用户，你是如何实现的？我们使用`$ne`操作符。`$ne`(不等于)运算符返回搜索字段的值不等于给定值的文档。该操作符也将返回不包含搜索字段的文档。

请考虑以下情况:

该查询将检索年龄不超过 45 岁的所有用户。

*   **$ not:**`$not`操作符对指定的查询操作符执行*翻转挑战*。假设您使用以下查询来选择 18 岁以上的用户:

在上述查询中使用`$not`操作符时，将选择 18 岁及以下的用户:

您可能想知道这与`$lte`操作符有什么不同。虽然`$lte`操作符将只选择具有年龄字段且其值小于或等于 18 的用户，但查询`{$not: { $gt: 18 }}`不仅会选择小于或等于 18 的用户，还会选择没有年龄字段的用户。

*   **$或:** `$or`将计算两个或更多表达式的数组，并将选择与至少一个表达式匹配的文档。

考虑下面的例子:

该查询包含两个表达式的数组。$or 运算符将计算这些表达式，并从用户集合中选择文档，其中`firstName` 字段值为`Serena` 或者`age` 字段值小于`40`。

如果没有符合这些表达式的文档，`$or`将不会检索到任何文档。

*   **$nor:** 因此，虽然`$or`操作符将选择至少匹配一个给定表达式的文档，但是`$nor`将选择不匹配数组中所有查询表达式的文档。`$nor`操作符也将选择不包含表达式中指定的搜索字段的文档。

将我们之前示例中的`$or`更改为`$nor`:

该查询将从用户集合中选择以下文档:

*   `firstName`字段值不等于`Serena`的用户
*   `age`字段值等于`40`及以上的用户
*   没有`firstName`和`age`字段的用户
*   **$exists:** 如果你需要检查一个特定的字段是否存在于一个文档中，使用`$exists`操作符。该运算符只能接受布尔值。当布尔值为`true`时，`$exists`将匹配包含该字段的文档，包括字段值为`null`的文档。如果布尔值为`false`，`$exists`将只匹配不包含该字段的文档。

请考虑以下情况:

该查询将只选择带有`age`字段的文档，即使该字段是`null`。如果布尔值被更改为`false`，查询将只选择没有`age`字段的文档。

在本指南中，我们研究了各种 MongoDB 查询，从基本的 CRUD 操作到更高级的查询，使用了:

*   读取选项(`sort`、`limit`、`skip`、`projection`)
*   比较查询运算符(`$lt`、`$gt`、`$lte`、`$gte`)
*   设置操作员(`$in`、`$all`、`$nin`)
*   布尔运算符(`$ne`、`$not`、`$or`、`$nor`、`$exists`)

我在写这篇文章的时候学到了很多，我希望你能从这篇文章中学到一些东西。

注意到这篇文章中有什么错误吗？请在评论部分指出这一点。我很乐意纠正它并加以改进。