# 用户分段

## 概述

本主题解释了如何构建和管理用户分段。用户分段可以让您根据个人或属性来定位用户群体。

## 理解用户分段

用户分段是用户列表，可以用来批量管理标志的定位行为。分段对于保持`beta-users`或`enterprise-customers`等用户群组的最新状态非常有用。它们可以让您更快地为特定的群体打开或关闭功能，并且更加有信心。

标志和分段定位之间有一些差异需要注意：

* 分段是特定环境的。它们不会在您创建它们的环境之外出现。
* 分段定位不能引用其他用户分段。

## 使用分段列表

您可以在**分段**列表上查看分段。从列表中，您可以按名称筛选分段。

![](../../feature-flags/assets/users-and-user-segments/user-segments/001.webp)

## 创建用户分段

要创建新的分段：

1. 导航到**分段**列表。
2. 点击**添加**。出现"添加分段"面板。

![](../../feature-flags/assets/users-and-user-segments/user-segments/002.webp)
3. 为您的分段设置一个可读的**名称**。
4. （可选）添加一个**描述**。
![](../../feature-flags/assets/users-and-user-segments/user-segments/003.webp)
5. 点击**保存**。分段的**定位**选项卡出现。

## 自定义用户分段

您可以在分段的**定位**选项卡中自定义分段，适用于不同的用户或属性，或者排除特定的用户和属性。分段定位规则与标志定位规则的功能相同。要了解更多信息，请阅读[定位用户](../targeting-users-with-flags/targeting-rules.md)。

要自定义分段：

1. 导航到要修改的用户分段的**定位**选项卡。
2. 使用**包括用户**或**排除用户**选项逐个定位用户。
![](../../feature-flags/assets/users-and-user-segments/user-segments/004.webp)
3. 点击**规则**旁边的**加号按钮**为该分段创建一个自定义规则。自定义规则菜单将出现：
![](../../feature-flags/assets/users-and-user-segments/user-segments/005.webp)
4. 指定规则的**属性**、**运算符**和**值**。
5. 如果要添加更多条件，点击规则条件旁边的**加号按钮**。
![](../../feature-flags/assets/users-and-user-segments/user-segments/006.webp)
6. 点击**保存**。

> 理解分段规则逻辑
>
> 当您为一个分段指定规则时，FeatBit会按照出现的顺序从上到下解析它们。根据您创建规则的顺序，您可以更改分段定位的应用方式。
>
> 如果用户符合其中一个规则，用户将被视为**包括用户**

## 删除分段

要删除分段，在**分段**列表中找到要删除的分段，然后点击**删除**。

![](../../feature-flags/assets/users-and-user-segments/user-segments/007.webp)

如果特性标志正在使用该分段，则应首先从特性标志中移除它。

![](../../feature-flags/assets/users-and-user-segments/user-segments/008.webp)