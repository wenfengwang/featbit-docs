# 用户属性

## 概述

本主题解释了用户属性是什么，它们对您在FeatBit中接收到的内容产生了什么影响，如何配置它们以及FeatBit如何使用它们来计算和显示用户的标记设置。

## 理解用户属性

用户可以是人、服务、机器或其他在您的应用中遇到特性标记的资源。任何唯一对应于目标的标识符都可以指定为用户。

更精确地说，一个用户可以被称为"用户对象"。用户对象是一个用户属性的集合，由唯一的用户密钥标识。它包括FeatBit在特性标记评估中可以使用的关于用户的所有信息。

FeatBit提供了两种类型的用户属性：内置属性和自定义属性。默认情况下，用户的两种类型的用户属性的值都会显示在**用户**列表中。

## 基于用户属性的定位

您可以在标记定位规则中使用内置和自定义的用户属性。例如，假设您希望一个标记对那些不属于`Test Segment`段并且其`Account`自定义属性不包含`test`的用户提供`true`变体。

以下是该规则的样子：

![](../../feature-flags/assets/users-and-user-segments/user-attributes/001.webp)

在设置了规则的条件之后，您可以决定您的用户是否会接收一个变体，还是在几个变体中进行百分比推出。要了解更多，请阅读[定位规则](../targeting-users-with-flags/targeting-rules.md)。

## 查看和管理用户

默认情况下，用户对象中的所有属性都会发送给FeatBit。这些数据使FeatBit能够确定用户的预期标记变体，并为整个FeatBit用户界面（UI）中的自动完成功能提供支持。

您可以从**用户**列表中访问用户页面。以下是FeatBit用户界面中的用户页面示例：

### 用户属性列表

![](../../feature-flags/assets/users-and-user-segments/user-attributes/002.webp)

### 用户特性标记列表

![](../../feature-flags/assets/users-and-user-segments/user-attributes/003.webp)

### 用户段列表

![](../../feature-flags/assets/users-and-user-segments/user-attributes/004.webp)