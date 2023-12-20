
# 用户属性

## 概览

本主题阐述了用户属性是什么、它们如何影响您在FeatBit中接收的内容、如何配置用户属性，以及FeatBit如何利用这些属性来计算和展示用户的特征标志设置。

## 理解用户属性

用户可以是人员、服务、机器或在您的应用中遇到特征标志的其他资源。任何能够唯一对应到一个目标的标识符都可以被定义为一个用户。

更精确地指代一个用户是使用“用户对象”。用户对象是由一个独特的用户键来标识的用户属性集合，它包含了FeatBit在特征标志评估中可能用到的关于用户的全部信息。

FeatBit提供了两种类型的用户属性：内建属性和自定义属性。默认情况下，用户的这两类属性值会显示在**用户**列表上。

## 基于用户属性的目标定位

您可以在特征标志的目标定位规则中使用内建和自定义用户属性。例如，设想您想要一个特征标志为那些不在“测试段”用户组中且其“账户”自定义属性不包含“test”的用户提供真值变量。

该规则如下所示：

![](../../feature-flags/assets/users-and-user-segments/user-attributes/001.webp)

在您设置好规则的条件后，您可以决定用户是接收单一变量，还是在多个变量中进行百分比分配。要了解更多信息，请阅读[目标定位规则](../targeting-users-with-flags/targeting-rules.md)。

## 查看和管理用户

默认情况下，您的用户对象中的所有属性都会被发送至FeatBit。这些数据使FeatBit能够确定用户预期的特征标志变体，并支持FeatBit用户界面（UI）中的自动完成功能。

您可以通过**用户**列表来访问用户页面。以下是FeatBit用户界面中的一些用户页面：

### 用户属性列表

![](../../feature-flags/assets/users-and-user-segments/user-attributes/002.webp)

### 用户特征标志列表

![](../../feature-flags/assets/users-and-user-segments/user-attributes/003.webp)

### 用户分组列表

![](../../feature-flags/assets/users-and-user-segments/user-attributes/004.webp)
