# 用户列表

## 概述

本主题介绍了**用户**列表是什么、如何生成以及如何使用它。

**用户**列表为您提供了一个汇总视图，显示每个用户如何体验应用中的所有功能，并允许您在一个屏幕上自定义他们的体验。您甚至可以为特定用户设置功能标志目标的过期日期，或移除针对个别用户的功能标志。

### 理解用户列表 

当用户遇到一个功能标志并被 FeatBit SDK 评估时，**用户**列表会自动填充。列表中的数据来自于您在变体调用中发送的用户数据，以及 identify 调用中的数据。

> **警告！** SDK 不使用**用户**列表上的属性来评估标志
>
> SDK 仅根据您在评估调用中提供的用户对象来评估标志。SDK 不使用显示在**用户**列表上的属性，用户属性也不会在 SDK 实例之间同步。您必须为每次评估提供所有相关的用户属性，以确保目标规则能够正确应用。

以下是**用户**列表的图片：

![](../../feature-flags/assets/users-and-user-segments/the-user-list/001.webp)

在列表中，您可以根据标准或自定义属性来过滤用户。

### 筛选用户 

您可以根据标准或自定义属性来筛选**用户**列表中的用户。

筛选用户的步骤如下：

1. 选择属性。![](../../feature-flags/assets/users-and-user-segments/the-user-list/002.webp)
2. 输入过滤值。![](../../feature-flags/assets/users-and-user-segments/the-user-list/003.webp)

目前仅支持字符串类型的筛选器。如果您需要更多类型的筛选器，请在 [FeatBit GitHub 的 issues 或讨论区](https://github.com/featbit/featbit)给我们反馈。

### 自定义用户列表

您可以自定义**用户**列表上显示的属性。开始操作前，请点击属性选择器。以下是列表上属性选择器的截图：

![](../../feature-flags/assets/users-and-user-segments/the-user-list/004.webp)

## 用户存储

**用户**列表展示了存储的用户信息。当一个用户的标志发送了 `identify` 或 `flag evaluation` 事件后，该用户会出现在列表上。用户信息不会自动删除。用户信息存储在 MongoDB 中。

## 删除用户

目前，您无法移除/删除用户。您可以在 [FeatBit GitHub 的 issues 或讨论区](https://github.com/featbit/featbit)发表您的反馈。您可以联系您的工程师在 MongoDB 数据库中删除用户。
