# 用户列表

## 概述

本主题介绍了**用户**列表是什么，它是如何填充的，以及如何使用它。

**用户**列表提供了对每个用户在应用程序中的所有功能中体验的概要视图，并允许您从一个屏幕上自定义他们的体验。您甚至可以为标志定向设置到期日期，或删除针对个别用户的标志。

### 理解用户列表

当用户遇到功能标志并被FeatBit SDK进行评估时，**用户**列表会自动填充。列表中的数据从您在变量调用中发送的用户数据以及身份识别调用中的数据进行填充。

> **警告！** SDK不使用**用户**列表上的属性来评估标志
>
> SDK仅根据您在评估调用中提供的用户对象评估标志。SDK不使用**用户**列表上显示的属性，并且用户属性在SDK实例之间不同步。您必须为每个评估提供所有适用的用户属性，以使定位规则正确应用。

下图显示了**用户**列表的图像：

![](../../feature-flags/assets/users-and-user-segments/the-user-list/001.webp)

您可以通过标准或自定义属性在**用户**列表上筛选用户。

### 筛选用户

您可以通过标准或自定义属性在**用户**列表上筛选用户。

要筛选用户：

1. 选择属性。
![](../../feature-flags/assets/users-and-user-segments/the-user-list/002.webp)
2. 输入筛选值。
![](../../feature-flags/assets/users-and-user-segments/the-user-list/003.webp)

它仅支持字符串类型的过滤器。如果您需要更多功能，请在[FeatBit GitHub的问题或讨论](https://github.com/featbit/featbit)中提供反馈。

### 自定义用户列表

您可以自定义在**用户**列表上显示的属性。首先，点击属性选择器。以下是列表上属性选择器的屏幕截图：

![](../../feature-flags/assets/users-and-user-segments/the-user-list/004.webp)

## 用户存储

**用户**列表显示了存储的用户信息。在标志为他们发送`identify`或`标志评估`事件之后，用户将出现在列表中。用户不会自动删除。用户信息存储在MongoDB中。

## 移除用户

目前，您无法删除用户。如果您想要删除用户，请在[FeatBit GitHub的问题或讨论](https://github.com/featbit/featbit)中发布您的反馈。您可以联系工程师删除MongoDB数据库中的用户。