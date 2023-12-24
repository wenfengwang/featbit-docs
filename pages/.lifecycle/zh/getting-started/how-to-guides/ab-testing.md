# AB 测试

**文档正在建设中。**

> 传统的实验工具倾向于支持前端实验，却忽略了后端实验。此外，它们往往无法很好地与您的软件部署流程集成。FeatBit 支持“全面实验”，让您可以在生产环境中无缝地运行前端和服务器端实验（包括多变量测试），并将实验与您的常规开发流程整合。

## 先决条件

我们假设您已经完成了“入门”系列教程中的最后三篇：

* 您已经在教程[为演示创建 2 个功能标志](../create-two-feature-flags.md)中成功创建了两个功能标志，`game runner` 和 `difficulty mode`。
* 您已经有了基本的经验，知道如何[与 "`Dino Game` 演示互动](../try-interacting-with-the-demo.md)。
* 您知道如何[连接 SDK](../connect-an-sdk/) 到您的程序或“Dino Game”演示：
  * 下载演示代码样本
  * 初始化 SDK
  * 用自定义属性识别用户
  * 实施一个功能标志来交付和控制功能

## DinoGame 演示容易理解吗？

您会看到，我们创建了一个 DinoGame，目的是让用户能够尽可能轻松地开始使用。但我们对初始流程设计的不同版本有不同意见。我们使用 AB 分组来测试结果，并尽可能使结果在统计上合理。我们创建了两组：

* 一个对照组，“Release Dino Game”作为演示的第一步。
* 一个实验组，“Difficulty mode”作为演示的第一步。

我们测试哪个版本更能帮助用户完成演示。

## 为每种模式创建相同的样本大小

我们让 10% 的用户在演示中首先看到“Difficulty mode”，90% 的用户首先看到“Release Dino Game”（这是初始设置）。

![](../../getting-started/assets/ab-testing/001.webp)

为了确保每个组都有相同的样本量，我们需要设置 AB 测试，使得对照组中的 1/9 用户（占总用户的 10%）参与测试。

![](../../getting-started/assets/ab-testing/002.webp)

## 当用户得分达到 500 分时创建指标

您需要为测试定义一个指标。在这里，您创建了一个转化指标。如果用户完成了整个流程，我们认为这是一次成功的转化。

![](../../getting-started/assets/ab-testing/003.webp)

## 为这个 AB 测试创建一个实验

返回到“概览”子面板，点击**添加**按钮。

![](../../getting-started/assets/ab-testing/004.webp)

在**实验**抽屉中，选择您之前创建的功能标志，选择“**demo completed**”作为指标，选择“**release dino game**”作为基准。点击**保存**按钮。

![](../../getting-started/assets/ab-testing/005.webp)

## 在项目中添加 AB 测试代码

您需要使用 FeatBit SDK 在 DinoGame 中添加以下代码：

* 添加 AB 测试功能标志以分割两个版本。

![](../../getting-started/assets/ab-testing/006.webp)

* 添加一个用于跟踪的度量事件，使用 fbClient.sendCustomEvent() 函数。

![](../../getting-started/assets/ab-testing/007.webp)

## 运行您的实验

在实验列表中，点击**检查结果**按钮，查看实验“demo process”的结果。

![](../../getting-started/assets/ab-testing/008.webp)

您将被引导至功能标志的**实验**标签页。点击实验中的开始按钮。实验开始运行！

![](../../getting-started/assets/ab-testing/009.webp)

## 查看测试结果与报告

随着时间的推移，我们可以在“实验”子标签页中逐渐看到实验报告。如果数据不足或控制差异不显著，我们会在下图中得到提示。

![](../../getting-started/assets/ab-testing/010.webp)

当数据充足且差异显著（例如 p 值小于 0.05）时，我们将得到哪个结果更优的指示，如下图所示，“Release Dino Game”胜出。

![](../../getting-started/assets/ab-testing/011.webp)
