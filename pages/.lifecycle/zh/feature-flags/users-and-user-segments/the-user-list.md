# 用户列表

## 概述

本主题将解释什么是“用户”列表，它是如何填充的，以及如何使用它。

**用户**列表为您提供了每个用户如何体验应用中所有功能的概览视图，并允许您从一个屏幕自定义他们的体验。您甚至可以为标志定位设置到期日期，或者移除针对单个用户的标志。

### 理解用户列表

当用户遇到功能标志并由 FeatBit SDK 评估时，“用户”列表会自动填充。列表中的数据是根据您在变体调用中发送的用户数据以及来自标识调用的数据填充的。

> **警告！** SDK 不使用“用户”列表上的属性来评估标志
>
> SDK仅根据您在评估调用中提供的用户对象来评估标志。SDK不使用用户列表上显示的属性，用户属性在SDK实例之间也不会同步。您必须为每次评估提供所有适用的用户属性，以便正确应用定位规则。

以下是“用户”列表的图像：

![](../../feature-flags/assets/users-and-user-segments/the-user-list/001.webp)

在列表中，您可以按标准或自定义属性筛选用户。

### 筛选用户

您可以按标准或自定义属性筛选“用户”列表中的用户。

要筛选用户：

1. 选择属性。
   ![](../../feature-flags/assets/users-and-user-segments/the-user-list/002.webp)
2. 输入筛选值。
   ![](../../feature-flags/assets/users-and-user-segments/the-user-list/003.webp)

它仅支持字符串类型的筛选器。如果您需要更多功能，请在[FeatBit GitHub的问题或讨论](https://github.com/featbit/featbit)中向我们提供反馈。

### 自定义用户列表

您可以自定义“用户”列表上显示的属性。首先，单击属性选择器。以下是列表上属性选择器的截图：

![](../../feature-flags/assets/users-and-user-segments/the-user-list/004.webp)

## 用户存储

“用户”列表显示存储的用户信息。用户在标志发送“identify”或“flag evaluation”事件后将出现在列表中。用户不会被自动删除。用户信息存储在MongoDB中。

## 删除用户

目前，您无法移除/删除用户。如果您有此需求，请在[FeatBit GitHub的问题或讨论](https://github.com/featbit/featbit)中提供反馈。您可以联系您的工程师删除MongoDB数据库中的用户。