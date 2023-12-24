# 用户分群

## 概述

本主题介绍了如何构建和管理用户分群。用户分群可以让您单独或按属性定位用户组。

## 理解用户分群

用户分群是用户列表，可用于批量管理标记定位行为。分群对于保持用户组（如 `beta-users` 或 `enterprise-customers`）的最新状态非常有用。它们使您可以更快地放心地为特定组打开或关闭功能。

标记定位和分群定位之间存在一些差异，您应该注意：

* 分群是特定于环境的。它们不会在创建它们的环境之外的环境中显示。
* 分群定位不能引用其他用户分群。

## 使用分群列表

您可以在**分群**列表中查看分群。在列表中，您可以按名称筛选分群。

![](../../feature-flags/assets/users-and-user-segments/user-segments/001.webp)

## 创建用户分群

要创建新的分群：

1. 导航到**分群**列表。
2. 单击**添加**。将显示“添加分群”面板。

![](../../feature-flags/assets/users-and-user-segments/user-segments/002.webp)
3. 为您的分群指定一个可读的**名称**。
4. （可选）添加**说明**。
![](../../feature-flags/assets/users-and-user-segments/user-segments/003.webp)
5. 点击**保存**。将显示分群的**定位**选项卡。

## 自定义用户分群

您可以在分群的**定位**选项卡中自定义分群，以应用于不同的用户或属性，或排除用户和属性。分群定位规则的功能与标记定位规则相同。要了解更多信息，请阅读[定位用户](../targeting-users-with-flags/targeting-rules.md)。

要自定义分群：

1. 导航到要修改的用户分群的**定位**选项卡。
2. 使用**包括用户**或**排除用户**选项单独定位用户。
![](../../feature-flags/assets/users-and-user-segments/user-segments/004.webp)
3. 单击**规则**旁边的**+**按钮，为此分群创建自定义规则。将显示自定义规则菜单：\
![](../../feature-flags/assets/users-and-user-segments/user-segments/005.webp)
4. 指定规则的**属性**、**运算符**和**值**。
5. 如果要添加更多条件，请单击规则条件旁边的**加号按钮**。
![](../../feature-flags/assets/users-and-user-segments/user-segments/006.webp)
6. 点击**保存**。

> 理解分群规则逻辑
>
> 当您为分群指定规则时，FeatBit会按照从上到下的顺序解析这些规则。您可以根据创建的规则顺序更改分群定位的应用方式。
>
> 如果用户符合其中一个规则，则用户将被视为**包含的用户**

## 删除分群

要删除分群，找到要删除的分群在**分群**列表中，然后单击**删除**。

![](../../feature-flags/assets/users-and-user-segments/user-segments/007.webp)

如果功能标记正在使用该分群，您应首先将其从功能标记中删除。

![](../../feature-flags/assets/users-and-user-segments/user-segments/008.webp)