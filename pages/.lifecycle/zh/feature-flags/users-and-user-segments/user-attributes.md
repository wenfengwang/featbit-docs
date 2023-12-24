# 用户属性

## 概述 

本主题将解释用户属性是什么，它们如何影响您在 FeatBit 中接收的内容，如何配置它们，以及 FeatBit 如何使用它们来计算和显示用户的标志设置。

## 了解用户属性 

用户可以是您的应用中遇到功能标志的人员、服务、计算机或其他资源。任何能唯一对应到目标的标识符都可以被指定为用户。

更精确地说，一个用户可以被称为"用户对象"。用户对象是用户属性的集合，由唯一的用户密钥标识。它包括了 FeatBit 在特性标志评估中可以使用的有关用户的所有信息。

FeatBit 提供两种类型的用户属性：内置属性和自定义属性。默认情况下，用户的这两种类型的属性值都会显示在**用户**列表中。

## 基于用户属性的定位

您可以在标志的定位规则中使用内置和自定义用户属性。例如，假设您希望一个标志对不属于`Test Segment`区段且其`Account`自定义属性不包含`test`的用户提供`true`变体。

规则如下所示：

![](../../feature-flags/assets/users-and-user-segments/user-attributes/001.webp)

当您设置好规则的条件后，您可以决定您的用户将收到一个变体，还是跨多个变体进行百分比推出。要了解更多信息，请阅读[定位规则](../targeting-users-with-flags/targeting-rules.md)。

## 查看和管理用户 

默认情况下，您的用户对象中的所有属性都会被发送到 FeatBit。这些数据让 FeatBit 能够确定用户的预期标志变体，并为 FeatBit 用户界面（UI）中的自动完成功能提供支持。

您可以从**用户**列表访问用户页面。以下是 FeatBit UI 中的用户页面：

### 用户属性列表

![](../../feature-flags/assets/users-and-user-segments/user-attributes/002.webp)

### 用户特性标志列表

![](../../feature-flags/assets/users-and-user-segments/user-attributes/003.webp)

### 用户细分列表

![](../../feature-flags/assets/users-and-user-segments/user-attributes/004.webp)