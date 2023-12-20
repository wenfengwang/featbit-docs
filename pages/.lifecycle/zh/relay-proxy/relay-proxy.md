
# 中继代理

## 概览

本主题将解释如何创建**FeatBit Relay Proxy**配置，并将**FeatBit Agent**连接至其中。如果您不了解**FeatBit Agent**是什么，请阅读这个[document](featbit-agent.md)。

## 代理状态

FeatBit UI展示以下几种代理状态：

* 健康：代理处于健康状态，一切运行正常。
* 不健康：代理出现问题。
* 无法访问：代理不可用。通常是因为代理尚未启动或代理主机URL不正确。
* 未授权：如果您看到此状态，意味着您启动FeatBit代理时使用的ApiKey与中继代理密钥不匹配。

## 限制创建和管理中继代理的权限

要能够创建Relay Proxy Configurationn，您必须具备**ManageRelayProxies**和**ListRelayProxies**权限，如果您拥有内置策略（拥有者、管理员、开发者）中的一个，您已经具备这些权限。

![](../relay-proxy/assets/relay-proxy/001.webp)

## 创建中继代理配置

您可以从**中继代理**页面创建一个中继代理配置。

1.  导航至**Relay Proxy**页面。

2. 点击页面右上角的**添加**按钮，将出现**添加中继代理**面板。\
![](../relay-proxy/assets/relay-proxy/003.png)
3. 为您的令牌起一个易于理解的**名称**并添加描述**。**
4. 设置作用域：选择您希望同步功能标志和细分到代理的环境。
5. 设置代理名称和主机
6. 点击**保存**按钮。
7. 将密钥复制并保存在安全的地方。离开此页面后，密钥将被隐藏。

![](../relay-proxy/assets/relay-proxy/004.png)

创建中继代理后，您可以编辑或删除它。您也可以在此页面管理现有的中继代理。

## 将功能标志和细分同步到代理

目前，我们只支持手动同步。要进行同步，请点击中继代理旁的“编辑”按钮，然后在编辑面板中点击“同步”按钮，选定的作用域内的功能标志和细分将同步到代理。

![](../relay-proxy/assets/relay-proxy/005.png)

## 检查FeatBit代理状态

代理可能会有不同的状态。要更新状态或调试问题，请点击状态标签，将弹出一个显示代理详细状态的模态框。**lastSyncAt**值显示的是UTC时区时间。

![](../relay-proxy/assets/relay-proxy/006.png)

## 管理中继代理

要管理中继代理，请执行以下步骤：

1. 导航至**Relay Proxies**页面。
2. 在列表中找到您的代理。
3. 点击**编辑**或**删除**按钮

您可以检查中继代理的状态：

* 当所有代理都处于健康状态时，状态颜色为**绿色**。
* 如果至少有一个代理不处于健康状态，状态颜色为**红色**。

![](../relay-proxy/assets/relay-proxy/007.png)

## 将FeatBit代理连接至FeatBit UI

在创建中继代理配置后，您应当将密钥保存在安全的地方，使用该密钥作为ApiKey参数值来启动FeatBit代理，请参阅[安装FeatBit代理](https://github.com/featbit/featbit-agent#installation)。
