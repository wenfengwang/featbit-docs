# 在生产环境中进行测试

> 什么是 **生产环境中的测试**
>
> 复制生产环境是不可能的。要了解功能在现实世界中的表现，唯一可靠的方法是与真实用户进行测试。功能标志提供了在生产环境中安全测试所需的控制。利用FeatBit的目标定位功能，将新功能暴露给特定的用户子集。如果系统性能受损，您可以中止推出并限制事件的影响范围。但如果一切顺利，您可以逐渐向更广泛的受众发布新功能。

## 先决条件

我们假设您已经完成了“入门”系列的最后三个教程：

* 您已在教程[为演示创建2个标志](../create-two-feature-flags.md)中成功创建了两个功能标志 `game runner` 和 `difficulty mode`。
* 您已经有了基本的经验，知道如何[与 "`Dino Game` 演示互动](../try-interacting-with-the-demo.md)"。
* 您知道如何[连接一个SDK](../connect-an-sdk/)到您的程序或“Dino Game”演示：
  * 下载演示代码样本
  * 初始化SDK
  * 用自定义属性识别用户
  * 实现一个功能标志来交付和控制功能

## 使用单个用户在生产环境中进行测试

游戏已经在线上部署。在向所有玩家发布之前，您想先与一些密切的朋友进行测试。您可以使用“目标用户”部分将您的朋友添加到“白名单”。

转到您的“game runner”功能标志的目标页面，展开“目标用户”部分。您将看到每个变体 `true` 和 `false` 下的两个选择列表。

要将您的朋友添加到“白名单”，我们只需要：

1. 将您朋友的游戏用户名添加到 `true` 下的选择列表中。
2. 打开功能标志。
3. 将默认规则设置为 `false`。

以上三个步骤告诉FeatBit，“game runner”功能标志已经打开。只有在“目标用户”部分的真实列表中的用户才能获得 `true` 变体（可以玩游戏）。

![](../../getting-started/assets/testing-in-production/001.webp)

### 用户来自哪里？

真实列表中的用户可以通过三种方式导入：

1. 在“数据同步”部分，您可以通过预定义的JSON文件将所有用户导入到FeatBit中。![](../../getting-started/assets/testing-in-production/002.webp)
2. 当用户在您的应用程序中注册时，用户信息会被保存到系统中。![](../../getting-started/assets/testing-in-production/003.webp)
3. 您也可以直接在“目标用户”选择列表中输入用户名。如果用户不存在，系统会在“终端用户”列表中添加一个新用户。

用户信息可以在“终端用户”页面中找到。

![](../../getting-started/assets/testing-in-production/004.webp)

## 使用 QA 组在生产环境中进行测试

您的朋友喜欢您的游戏，他们希望能够总是在向公众发布之前先测试新功能。他们成为了可重复使用的测试用户（类似QA团队）。为了让我们下次发布新功能时工作更加轻松，您可以创建一个名为“my lovely QA team”的QA组，每次部署游戏的新功能时都会使用这个组。

转到“Segments”页面，创建一个名为“my lovely QA team”的组。

![](../../getting-started/assets/testing-in-production/005.webp)

在组详细信息页面，我们将我可爱的测试用户添加到“包含用户”列表中，然后点击保存。这个组可以跨不同的功能标志共享。

![](../../getting-started/assets/testing-in-production/006.webp)

我们回到功能标志列表并打开“game runner”功能标志的“目标”页面。

1. 移除“目标用户”部分真实列表中的所有用户。
2. 将“my lovely QA team”添加到自定义规则中。
   1. 添加一个新的自定义规则并命名它（例如，“生产环境测试规则”）。
   2. 选择“用户在组中”作为IF条件。
   3. 在部分列表中选择“my lovely QA team”。
   4. 在服务区域选择 `true`。

![](../../getting-started/assets/testing-in-production/007.webp)

上述配置意味着，如果用户在“my lovely QA team”组中，DinoGame将向该用户发布。这个配置也可以在其他功能标志中实施，以便在生产环境中测试其他功能，如“difficulty mode”。

![](../../getting-started/assets/testing-in-production/008.webp)

这个组也被称为可重用组，它可以跨不同的功能标志使用。更新一个组意味着更新所有使用这个组的功能标志。
