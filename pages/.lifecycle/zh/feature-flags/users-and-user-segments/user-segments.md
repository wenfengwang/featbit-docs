
# 用户细分

## 概览

本主题将阐述如何构建和管理用户细分。用户细分使您能够针对个体用户或按属性划分的用户群体进行定位。

## 理解用户细分

用户细分是一种用户列表，您可以利用它来批量管理功能标记的定位行为。细分对于保持像测试用户或企业客户这样的用户群组信息的更新非常有用。它们让您能够更加迅速且有信心地为特定群组开启或关闭功能。

在功能标记定位和细分定位之间，有一些您需要了解的差异：

* 细分是特定于环境的。它们不会在您创建它们的环境之外的其他环境中显示。
* 细分定位不能引用另一个用户细分。

## 使用细分列表

您可以在**细分**列表上查看细分。从列表中，您可以按名称筛选细分。

![](../../feature-flags/assets/users-and-user-segments/user-segments/001.webp)

## 创建用户细分

要创建新的细分，请按照以下步骤操作：

1. 导航至**细分**列表。
2.  点击 **添加**。"添加细分"面板会出现。

![](../../feature-flags/assets/users-and-user-segments/user-segments/002.webp)
3. 为您的细分命名一个易于理解的**名称**。
4. （可选）添加**描述**。
![](../../feature-flags/assets/users-and-user-segments/user-segments/003.webp)
5. 点击**保存**。细分的**定位**标签页将会显示出来。

## 自定义用户细分

您可以自定义一个段以适用于不同的用户或属性，或在细分的**定位**标签页中排除用户和属性。细分定位规则的工作方式与标志定位规则相同。要了解更多信息，请阅读[Targeting users](../targeting-users-with-flags/targeting-rules.md)。

要自定义一个细分，请：

1. 导航至您想要修改的用户细分的**定位**标签页。
2.  通过选择**包括用户**或**排除用户**选项来单独定位用户。
![](../../feature-flags/assets/users-and-user-segments/user-segments/004.webp)
3.  点击 **+** 按钮旁边的**规则**，为该细分创建自定义规则。自定义规则菜单将会出现：\
![](../../feature-flags/assets/users-and-user-segments/user-segments/005.webp)
4. 为规则指定**属性**、**运算符**和**值**。
5.  如果您想添加更多条件，请点击**加号按钮**旁边的规则条件。
![](../../feature-flags/assets/users-and-user-segments/user-segments/006.webp)
6. 点击**保存**。

> 理解**细分**规则逻辑
> 当您为一个细分指定规则时，FeatBit 会按照它们出现的顺序从上到下进行解析。您可以通过改变您创建的规则的顺序来调整细分定位的应用方式。
> 如果用户符合其中一个规则，用户就会被视为**包括用户**

## 删除细分

要删除一个细分，只需在**细分**列表中找到您想要删除的细分，然后点击**移除**。

![](../../feature-flags/assets/users-and-user-segments/user-segments/007.webp)

如果一个功能标记正在使用该细分，您应该先从功能标记中移除它。

![](../../feature-flags/assets/users-and-user-segments/user-segments/008.webp)
