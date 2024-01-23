# AB 测试

**文档正在建设中。**

> 传统的实验工具倾向于支持前端实验，同时忽视了后端实验。此外，它们往往无法很好地与您的软件部署流程集成。FeatBit 支持“全面实验”，使您能够在生产环境中无缝地运行前端和服务器端实验（包括多变量测试）。并且它能将实验与您的常规开发流程整合。

## 先决条件

我们假设你已经完成了“入门”中的最后三个教程：

* 您已在教程[为演示创建2个标志](../create-two-feature-flags.md)中成功创建了两个功能标志：`game runner`和`difficulty mode`。
* 您对如何[与“`Dino Game`”演示进行交互](../try-interacting-with-the-demo.md)有基本经验。
* 您知道如何[连接一个 SDK](../connect-an-sdk/)到您的程序或者“恐龙游戏”演示：
  * 下载一个演示代码样本
  * 初始化 SDK
  * 使用自定义属性来识别用户。
  * 实现一个功能标志以交付并控制该功能

## DinoGame Demo 容易理解吗？

您会看到，我们为那些希望尽可能轻松开始的用户创建了一个DinoGame。但我们对最初流程设计的不同版本有所分歧。我们使用AB组来测试结果，我们尽可能使结果在统计学上显得合理。我们创建了两组：

* 一个对照组，“Release Dino Game”是演示的第一步。
* 一个实验组，“难度模式”将是演示中的第一步。

我们测试哪一个更适合让人们完成演示。

## 为每种模式创建相同的样本大小

我们让10%的用户在演示中首先看到“困难模式”，而90%的用户首先看到的是“释放恐龙游戏”（这是初始设置）。


![](../../getting-started/assets/ab-testing/001.webp)

为了保持每个组的样本量相同，我们需要设置 AB 测试，使得对照组中的 1/9 用户（占总用户的 10%）被纳入测试。

![](../../getting-started/assets/ab-testing/002.webp)

## 当用户得到500分时创建指标

您需要为测试定义一个指标。您在这里创建一个转化指标。如果用户完成了整个过程，我们认为这是一次成功的转化。

![](../../getting-started/assets/ab-testing/003.webp)

## 为这个AB测试创建一个实验

返回“概述”子面板，然后单击**添加**按钮

![](../../getting-started/assets/ab-testing/004.webp)

在**实验**抽屉中，选择上面创建的特性标志，选择**演示完成**作为指标，选择**发布恐龙游戏**作为基准。点击**保存**按钮。

![](../../getting-started/assets/ab-testing/005.webp)

## 在项目中添加 AB 测试代码

您需要使用 FeatBit SDK 在 DinoGame 中添加以下代码：

* 添加 AB 测试特性标志以分离两个版本。

![](../../getting-started/assets/ab-testing/006.webp)

* 使用 fbClient.sendCustomEvent() 函数添加用于跟踪的指标事件。

![](../../getting-started/assets/ab-testing/007.webp)

## 进行你的实验

在实验列表中，点击实验**demo process**的**检查结果**按钮。

![](../../getting-started/assets/ab-testing/008.webp)

你将被引导至功能标志**“实验”**标签页。点击实验中的“开始”按钮。它开始运行！

![](../../getting-started/assets/ab-testing/009.webp)

## 查看测试结果与报告

随着时间的变化，我们可以在“实验”子标签中逐渐看到实验报告。如果数据不足，或者控制组差异不显著，我们会在下图中得到提示。

![](../../getting-started/assets/ab-testing/010.webp)

当数据充分且差异显著（例如 p 值小于 0.05）时，我们将得到哪个结果更优的指示，如下图所示，“发布恐龙游戏”胜出。

![](../../getting-started/assets/ab-testing/011.webp)