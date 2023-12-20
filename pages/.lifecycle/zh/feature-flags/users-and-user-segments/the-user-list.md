
# 用户列表

## 概览

本主题旨在解释什么是**用户**列表，它是如何生成的以及如何使用它。

**用户列表**提供了一个关于每位用户如何体验应用中所有功能的总览，并允许您在同一界面上自定义他们的体验。您甚至可以为特定功能的目标设置过期时间，或者移除针对个别用户的功能标记。

### 理解用户列表

当用户触发一个功能标记并被FeatBit SDK评估时，**用户**列表会自动生成。列表中的数据来源于您在变体调用中传递的用户数据，以及identify调用中的数据。

> **警告！**SDK不会利用用户列表上的属性来评估**标记**
> SDK仅基于您在评估调用中提供的用户对象来评估标记。SDK不会使用**用户**列表上显示的属性，且用户属性不会在不同SDK实例间同步。您必须为每一次评估提供所有相关的用户属性，以确保目标规则能够正确应用。

以下是**用户**列表的图片：

![](../../feature-flags/assets/users-and-user-segments/the-user-list/001.webp)

通过列表，您可以根据标准或自定义属性对用户进行筛选。

### 筛选用户

您可以根据标准或自定义属性对**用户**列表上的用户进行筛选。

筛选用户的步骤如下：

1. 选择属性。
![](../../feature-flags/assets/users-and-user-segments/the-user-list/002.webp)
2. 输入筛选值。
![](../../feature-flags/assets/users-and-user-segments/the-user-list/003.webp)

目前仅支持字符串类型的筛选器。如果您希望支持更多类型，请在[FeatBit GitHub的问题追踪或讨论区](https://github.com/featbit/featbit)给我们反馈。

### 自定义用户列表

您可以自定义用户列表上显示哪些属性。开始操作时，请点击属性选择器。以下是列表上**属性选择器**的截图：

![](../../feature-flags/assets/users-and-user-segments/the-user-list/004.webp)

## 用户存储

**用户**列表展示了存储的用户信息。用户在发送了`identify`或`flag evaluation`事件后，会显示在列表上。用户信息不会自动删除，而是存储在MongoDB中。

## 移除用户

目前，您还不能移除/删除用户。您可以在[FeatBit GitHub的问题追踪或讨论区](https://github.com/featbit/featbit)发布您的反馈。您也可以联系您的工程师在MongoDB数据库中删除用户。
