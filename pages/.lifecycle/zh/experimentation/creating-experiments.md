
# 创建实验

## 概览

本主题阐述了如何在FeatBit中搭建和配置实验。它介绍了度量指标的概念，阐释了不同类型的度量指标，并讲解了度量指标与功能标志如何互动以打造实验。

在FeatBit中，度量指标与标志的结合便构成了一个实验。实验能够让您通过将功能标志映射到团队关注的度量指标上，来衡量这些标志对用户的影响。

## 创建度量指标

度量指标是评价功能标志事件的衡量标准。您可以利用度量指标来追踪从用户访问URL的频次到URL页面加载时间等各种数据。如果用户加载了某个URL、点击了某个元素，或以其他方式参与了度量指标所追踪的行为，那么您可以通过FeatBit SDK来将事件记录到您的实验中。

您不需要为每个新实验都创建新的度量指标。您可以在多个实验中复用已有的度量指标，这让您可以比较同一度量指标在不同功能标志下的表现。同样地，一个实验可以使用主要和辅助度量指标，从而观察不同变量在各种度量上的表现。

### 使用主要和辅助度量指标

您可以在实验中只设定一个度量指标作为主要度量指标，但如果您希望追踪更多的度量表现，您可以添加辅助度量指标。我们建议每个实验中使用的度量指标不超过十个。

主要度量指标有时也被称作“总体评价准则”。在决定实验中的胜出变量时，您应该仅依据主要度量指标进行决策，因为当决策涉及多个度量指标时，会变得更加复杂。

如果您只使用一个度量指标，那么结果只有两种可能：增加或减少。如果您使用两个度量指标，那么将有四种可能的结果组合：增加/减少，减少/增加，增加/增加，或减少/减少。

每增加一个度量指标，可能的结果组合就会迅速增加。如果您使用三个度量指标，那么将有八种不同的可能结果组合。如果您使用十个度量指标，那么将有1024种可能的结果组合。因此，我们建议您在决策时仅依据主要度量指标。

### 度量指标类型

下表说明了您可以用度量指标来追踪的事件类型及其SDK兼容性：

<table><thead><tr><th width="217.33333333333331">Metric type</th><th>Description &#x26; Example uses</th></tr></thead><tbody><tr><td>Click conversion</td><td>Tracks the clicks on a user interface (UI) element.<br><br>- How often do users click a "Save" button? <br>- How many times do users click on a link? <br>- When is the best point during a process to display a sign-up invitation?</td></tr><tr><td>Custom conversion</td><td>Tracks events for any arbitrary event.<br><br>- Do user searches call a particular service? <br>- Do customers contact customer service within a set period of time? <br>- Do customers renew their contract within 30 days? Do user payments succeed?</td></tr><tr><td>Page view conversion</td><td>Tracks how many times a page is viewed.<br><br>- How many times do users view a blog post?</td></tr><tr><td>Custom numeric</td><td>Tracks increases or decreases in numeric value against a baseline you set.<br><br>- How much do users spend per transaction in my store? <br>- How much do users spend in total? <br>- How many items do users purchase per transaction? <br>- How many items do users purchase total? <br>- How much time do users spend on a page? <br>- How long does it take for a server to respond to a request? <br>- How long until the time to first byte (TTFB)?</td></tr></tbody></table>


### 创建度量指标

前往**实验**页面，在**度量**标签页下，点击**新增度量指标**按钮。

![](../experimentation/assets/creating-experiments/001.webp)

在度量指标抽屉中，填写度量指标的信息。

![](../experimentation/assets/creating-experiments/002.webp)

* 名称：度量指标的名称
* 描述：（可选）度量指标的描述
* 维护人：此度量指标的负责人
* 事件类型：FeatBit目前仅支持自定义事件类型，但实际上也支持以下类型：
  * 自定义转化，您需要在选择器下方选择**转化率**
  * 自定义数值，您需要在选择器下方选择**数值**
  * 点击转化和页面浏览转化：这些可以被当作自定义转化处理
* 事件名称：将在FeatBit实验评估中用于识别事件的名称。调用SDK追踪事件时，需要将此名称作为参数传递。
* 单位：当您选择“数值”作为事件类型时，这将用来标识您正在衡量的数值类型。
* 胜出标准：通过选择“高于基准线”或“低于基准线”来定义胜出标准

## 创建一个实验

返回到“概览”子面板并点击**添加**按钮。

![](../experimentation/assets/creating-experiments/003.webp)

在**实验**抽屉中，选择您之前创建的功能标志，选择一个**度量**，选择一个变量作为基准。点击**保存**按钮。

![](../experimentation/assets/creating-experiments/004.webp)

## 运行实验

在实验列表中，点击按钮**检查实验结果**。

![](../experimentation/assets/creating-experiments/005.webp)

您将被带到功能标志的**实验**标签页。点击实验中的“开始”按钮，实验就开始运行了！

![](../experimentation/assets/creating-experiments/006.webp)

## 创建实验受众群体

您可以运行一个实验来测试一个标志的默认规则，或者您可以创建一个自定义实验受众群体，通过选择特定的标志定位规则来包含在您的实验中。您可以根据您收集到的任何用户属性来设定目标。要了解详情，请阅读[目标规则](../feature-flags/targeting-users-with-flags/targeting-rules.md)。

在搭建实验时，您可以分配全部或一部分遇到功能标志的用户流量给实验。受众分配为您选择实验受众提供了灵活性，并确保了实验结果的准确性。FeatBit仅分析那些您选择加入实验的用户。

您可以通过点击按钮**设置A/B测试规则**来选择特定的标志目标规则。

![](../experimentation/assets/creating-experiments/007.webp)

您可以在抽屉面板中配置具体的A/B测试流量。下图仅展示了10%匹配默认规则的总用户被包含在实验中。80%匹配v1默认规则的用户被排除在实验之外。

![](../experimentation/assets/creating-experiments/008.webp)
