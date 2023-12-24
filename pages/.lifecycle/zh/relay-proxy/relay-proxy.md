# Relay Proxy

## 概览

本主题介绍如何创建 FeatBit Relay Proxy 配置，以及如何将 FeatBit Agent 连接到它。如果您不了解 FeatBit Agent，请阅读此[文档](featbit-agent.md)。

## 代理状态

FeatBit UI 显示以下代理状态：

* 健康：代理处于健康状态，一切正常
* 不健康：代理存在问题
* 无法到达：代理不可用。这通常是因为代理尚未启动或代理主机 URL 不正确
* 未授权：如果您看到这个状态，意味着您用来启动 FeatBit Agent 的 ApiKey 与中继代理密钥不匹配

## 限制创建和管理 Relay Proxy 的用户

要能够创建 Relay Proxy 配置，您必须具有 **ManageRelayProxies** 和 **ListRelayProxies** 权限，如果您拥有内置策略（Owner、Administrator、Developer）中的一个，您已经具有这些权限。

![](../relay-proxy/assets/relay-proxy/001.webp)

## 创建 Relay Proxy 配置

您可以从 **Relay Proxies** 页面创建 Relay Proxy 配置。

1. 导航到 **Relay Proxy** 页面。

![](../relay-proxy/assets/relay-proxy/002.png)
2. 点击页面右上角的 **Add** 按钮，**Add Relay Proxy** 面板会出现\
![](../relay-proxy/assets/relay-proxy/003.png)
3. 为您的令牌提供一个易于理解的 **Name** 和描述**。**
4. 设置作用域：选择您希望同步功能标志和细分市场到代理的环境。
5. 设置代理名称和主机
6. 点击 **Save** 按钮。
7. 复制并将密钥保存在安全的地方。离开此页面后，密钥将被隐藏。

![](../relay-proxy/assets/relay-proxy/004.png)

创建 Relay Proxy 后，您可以编辑或删除它。您也可以从这个页面管理现有的 Relay Proxy。

## 将功能标志和细分市场同步到代理

目前，我们只支持手动同步。要进行同步，请点击 Relay Proxy 的 **Edit** 按钮，然后在编辑面板中点击 **Sync** 按钮，所选作用域的功能标志和细分市场将同步到代理。

![](../relay-proxy/assets/relay-proxy/005.png)

## 检查 FeatBit Agent 状态

代理可以有不同的状态。要更新或调试代理的状态，请点击状态标签，一个显示代理详细状态的模态框会出现。**lastSyncAt** 的值是 UTC 时间。

![](../relay-proxy/assets/relay-proxy/006.png)

## 管理 Relay Proxy

要管理 Relay Proxy：

1. 导航到 **Relay Proxies** 页面。
2. 在列表中找到您的代理。
3. 点击 **edit** 或 **remove** 按钮

您可以检查 Relay Proxy 的状态：

* 当所有代理都处于健康状态时，颜色显示为 **green**
* 如果至少有一个代理不处于健康状态，颜色显示为 **red**

![](../relay-proxy/assets/relay-proxy/007.png)

## 将 FeatBit Agent 连接到 FeatBit UI

创建 Relay Proxy 配置后，您应该已经将密钥保存在某个安全的地方，使用该密钥作为 ApiKey 参数值来启动 FeatBit Agent，请阅读[安装 FeatBit Agent](https://github.com/featbit/featbit-agent#installation)。
