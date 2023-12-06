# Relay 代理

## 概述

本主题将解释如何创建一个 FeatBit Relay 代理配置，以及如何将 FeatBit 代理连接到它。如果您不知道什么是 FeatBit 代理，请阅读此[文档](featbit-agent.md)。

## 代理状态

FeatBit UI 显示以下代理状态：

* 健康: 代理处于正常状态，一切都正常工作。
* 不健康: 代理出现问题。
* 无法访问: 代理不可用。这通常是因为代理没有启动或者代理主机 URL 不正确。
* 未授权: 如果您看到这个，意味着您用来启动 FeatBit 代理的 ApiKey 与中继代理密钥不匹配。

## 限制谁可以创建和管理中继代理

要能够创建中继代理配置，您必须具有**ManageRelayProxies**和**ListRelayProxies**权限，如果您拥有内置策略之一 （Owner，Administrator，Developer），则已经具有这些权限。

![](../relay-proxy/assets/relay-proxy/001.webp)

## 创建中继代理配置

您可以从**Relay Proxies**页面创建中继代理配置。

1. 导航到**Relay Proxy**页面。

![](../relay-proxy/assets/relay-proxy/002.png)

2. 点击页面右上角的**添加**按钮，**添加 Relay Proxy**面板出现。

![](../relay-proxy/assets/relay-proxy/003.png)

3. 给您的令牌一个可阅读的**名称**和**描述**。

4. 设置范围：选择要将特性标志和段同步到代理的环境。

5. 设置代理名称和主机。

6. 点击**保存**按钮。

7. 在某个安全的地方复制并保存密钥。在离开此页面后，密钥将被遮蔽。

![](../relay-proxy/assets/relay-proxy/004.png)

创建了一个中继代理后，您可以编辑或删除它。您还可以从此页面管理现有的中继代理。

## 将特性标志和段同步到代理

目前，我们仅支持手动同步。要执行此操作，请单击中继代理的编辑按钮，然后在编辑面板中单击同步按钮，然后所选范围的特性标志和段将被同步到代理。

![](../relay-proxy/assets/relay-proxy/005.png)

## 检查 FeatBit 代理状态

代理可以具有不同的状态。要更新它或调试是否有问题，点击状态标签，将出现一个模态框显示代理的详细状态。**lastSyncAt** 值以 UTC 时间为准。

![](../relay-proxy/assets/relay-proxy/006.png)

## 管理中继代理

要管理中继代理：

1. 导航到**Relay Proxies**页面。

2. 在列表中找到您的代理。

3. 点击**编辑**或**删除**按钮。

您可以检查中继代理的状态：

* 当其所有代理处于健康状态时，颜色为**绿色**。

* 如果至少有一个代理处于不健康状态，则颜色为**红色**。

![](../relay-proxy/assets/relay-proxy/007.png)

## 连接 FeatBit 代理到 FeatBit UI

创建中继代理配置后，您应该在某个地方保存了密钥，将该密钥用作启动 FeatBit 代理的 ApiKey 参数值，请阅读 [安装 FeatBit 代理](https://github.com/featbit/featbit-agent#installation)。