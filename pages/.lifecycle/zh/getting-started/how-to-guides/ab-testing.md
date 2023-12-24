# AB 测试

**文档正在编写中。**

> 传统的实验工具往往支持前端实验，而忽略了后端实验。此外，它们通常无法很好地与您的软件部署过程集成。FeatBit 支持“全面实验”，让您能够在生产环境中无缝运行前端和服务器端实验（包括多变量测试）。它将实验与您的正常开发过程集成在一起。

## 先决条件

我们假设您已经完成了“入门”中的最后三个教程：

* 您已成功在教程[创建两个功能标志](../create-two-feature-flags.md)中创建了两个特性标志，`game runner` 和 `difficulty mode`。
* 您对如何与“Dino Game”演示进行交互具有基本经验，可以参考[与演示交互的尝试](../try-interacting-with-the-demo.md)。
* 您知道如何将 SDK 连接到您的程序或“Dino Game”演示：
  * 下载演示代码示例
  * 初始化 SDK
  * 使用自定义属性标识用户。
  * 实现功能标志以交付和控制功能。

## DinoGame 演示易于理解吗？

您会看到，我们为用户创建了一个 DinoGame，让他们能够尽快上手。但是，我们对初始流程设计的不同版本存在分歧。我们使用 AB 组来测试结果，以使结果在统计上尽可能合理。我们创建了两个组：

* 一个对照组，“发布 Dino Game”是演示的第一步。
* 一个实验组，“难度模式”是演示的第一步。

我们测试哪个更适合让用户完成演示。

## 为每个模式创建相同的样本数量

我们让 10% 的用户在演示中看到“难度模式”作为第一步，90% 的用户看到“发布 Dino Game”作为第一步（即初始化设置）。

![](../../getting-started/assets/ab-testing/001.webp)

为了确保每个组具有相同的样本量，我们需要设置 AB 测试，即在对照组中考虑 1/9 的用户（总用户数的 10%）。

![](../../getting-started/assets/ab-testing/002.webp)

## 当用户获得 500 分时创建指标

您需要为测试定义一个指标。在这里，您创建了一个转化指标。如果用户完成了整个过程，我们将其视为成功的转化。

![](../../getting-started/assets/ab-testing/003.webp)

## 为此 AB 测试创建实验

返回到“概述”子面板，然后单击“**添加**”按钮。

![](../../getting-started/assets/ab-testing/004.webp)

在**实验**抽屉中，选择您上面创建的功能标志，选择**演示已完成**作为指标，选择**发布 Dino Game**作为基准。然后单击**保存**按钮。

![](../../getting-started/assets/ab-testing/005.webp)

## 在项目中添加 AB 测试代码

您需要使用 FeatBit SDK 在 DinoGame 中添加以下代码：

* 添加 ab 测试功能标志以拆分两个版本。

![](../../getting-started/assets/ab-testing/006.webp)

* 使用 fbClient.sendCustomEvent() 函数添加用于跟踪的指标事件。

![](../../getting-started/assets/ab-testing/007.webp)

## 运行您的实验

在实验列表中，单击**检查实验演示过程结果**按钮。

![](../../getting-started/assets/ab-testing/008.webp)

您将被定向到功能标志**实验**选项卡。单击实验中的**开始**按钮。实验开始运行！

![](../../getting-started/assets/ab-testing/009.webp)

## 查看测试结果和报告

随着时间的推移，您可以在“实验”子选项卡中查看实验报告。如果数据不足，或者控制差异不显著，我们将收到下图中的提示。

![](../../getting-started/assets/ab-testing/010.webp)

当数据充足且差异显著（例如 p 值小于 0.05）时，我们将收到哪个结果更胜一筹的指示，如下图所示，“发布 Dino Game”获胜。

![](../../getting-started/assets/ab-testing/011.webp)