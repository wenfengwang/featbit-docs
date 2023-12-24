# 用户属性

## 概览 

本主题解释了什么是用户属性、它们如何影响您在FeatBit中接收的内容、如何配置它们，以及FeatBit如何利用它们来计算和展示用户的特性标志设置。

## 理解用户属性 

用户可以是应用中遇到特性标志的人、服务、机器或其他资源。任何能唯一对应到一个目标的标识符都可以被指定为用户。

更精确地说，一个用户可以被称为“用户对象”。用户对象是由唯一的用户键标识的用户属性集合。它包含了FeatBit在特性标志评估中可以使用的关于用户的所有信息。

FeatBit提供两种用户属性：内置属性和自定义属性。默认情况下，用户的内置属性和自定义属性的值都会显示在**用户**列表中。

## 基于用户属性的目标定位

您可以在特性标志的目标定位规则中使用内置和自定义用户属性。例如，假设您想让一个特性标志为不在`Test Segment`细分中且其`Account`自定义属性不包含`test`的用户提供`true`变体。

这是该规则的样子：

![](../../feature-flags/assets/users-and-user-segments/user-attributes/001.webp)

设置规则条件后，您可以决定用户是接收单一变体，还是在多个变体之间进行百分比分配。要了解更多，请阅读[目标定位规则](../targeting-users-with-flags/targeting-rules.md)。

## 查看和管理用户 

默认情况下，您的用户对象中的所有属性都会被发送到FeatBit。这些数据让FeatBit能够为用户确定预期的特性标志变体，并在FeatBit用户界面（UI）中提供自动完成功能。

您可以从**用户**列表访问用户页面。以下是FeatBit UI中的用户页面：

### 用户属性列表

![](../../feature-flags/assets/users-and-user-segments/user-attributes/002.webp)

### 用户特性标志列表

![](../../feature-flags/assets/users-and-user-segments/user-attributes/003.webp)

### 用户细分列表

![](../../feature-flags/assets/users-and-user-segments/user-attributes/004.webp)
