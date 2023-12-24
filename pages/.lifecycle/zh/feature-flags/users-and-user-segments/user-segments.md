# 用户细分

## 概述

本主题解释如何构建和管理用户细分。用户细分让您可以针对不同的用户群体进行个别或按属性的定位。

## 了解用户细分 

用户细分是您可以用来批量管理特性标志定位行为的用户列表。细分对于保持用户群组，如 `beta-users` 或 `enterprise-customers` 的更新非常有用。它们允许您更快速地对特定群组开启或关闭功能，并且更有信心。

在特性标志和用户细分定位之间有一些不同之处，您应该了解：

* 细分是特定于环境的。它们不会在创建它们的环境之外的其他环境中显示。
* 用户细分定位不能引用另一个用户细分。

## 使用细分列表 

您可以在 **细分** 列表中查看细分。从列表中，您可以按名称过滤细分。

![](../../feature-flags/assets/users-and-user-segments/user-segments/001.webp)

## 创建用户细分 

要创建一个新的细分：

1. 导航至 **细分** 列表。
2.  点击 **添加**。"添加细分"面板将出现。

![](../../feature-flags/assets/users-and-user-segments/user-segments/002.webp)
3. 为您的细分命名一个便于人类阅读的 **名称**。
4. （可选）添加一个 **描述**。
![](../../feature-flags/assets/users-and-user-segments/user-segments/003.webp)
5. 点击 **保存**。细分的 **目标** 选项卡将出现。

## 自定义用户细分 

您可以在细分的 **目标** 选项卡中自定义细分，以适用于不同的用户或属性，或者排除某些用户和属性。细分定位规则的功能与特性标志定位规则相同。要了解更多，请阅读[定位用户](../targeting-users-with-flags/targeting-rules.md)。

要自定义一个细分：

1. 导航至您希望修改的用户细分的 **目标** 选项卡。
2.  使用 **包括用户** 或 **排除用户** 选项来单独定位用户。
![](../../feature-flags/assets/users-and-user-segments/user-segments/004.webp)
3.  点击 **规则** 旁边的 **+** 按钮，以为此细分创建自定义规则。自定义规则菜单将出现：\
![](../../feature-flags/assets/users-and-user-segments/user-segments/005.webp)
4. 为规则指定一个 **属性**、一个 **运算符** 和 **值**。
5.  如果您想添加更多条件，请点击规则条件旁边的 **加号按钮**。
![](../../feature-flags/assets/users-and-user-segments/user-segments/006.webp)
6. 点击 **保存**。

> 理解细分规则逻辑
>
> 当您为一个细分指定规则时，FeatBit 会按照规则出现的顺序从上到下进行解析。您可以通过改变您创建的规则的顺序来改变细分定位的应用方式。
>
> 如果用户符合其中一个规则，该用户就被视为 **包括用户**

## 删除细分 

要删除一个细分，请在 **细分** 列表中找到您想要删除的细分，然后点击 **删除**。

![](../../feature-flags/assets/users-and-user-segments/user-segments/007.webp)

如果一个特性标志正在使用该细分，您应该先从特性标志中移除它。

![](../../feature-flags/assets/users-and-user-segments/user-segments/008.webp)
