# 标准版 VS. 专业版

之前，部署 FeatBit 较为困难，因为它依赖众多组件。对于小型企业而言，许多依赖并非必需。因此，我们通过移除对 ClickHouse、Kafka 和 Zookeeper 的依赖，推出了一个精简版。我们将这个精简版设为默认的标准版，并将完整版重命名为 FeatBit Professional。

* 标准版非常适合小型企业，而专业版则非常适合中大型企业。
* 标准版和专业版都是**可扩展且快速**的，并且**功能完全相同**。
* 标准版是一个更加**轻量级**的选择，仅依赖于 Redis 和 MongoDB。
* 专业版更为**庞大**，依赖于 Redis、MongoDB、Kafka、Zookeeper 和 ClickHouse。
* 对于标准版来说，Redis 是首选的消息队列，而专业版则使用 Kafka。
* MongoDB 是标准版首选的数据分析工具，而专业版则使用 ClickHouse。

