# 标准版 VS 专业版

以前，部署 FeatBit 有点困难，因为它有太多的依赖项。其中许多对于小型企业来说并不是必需的。因此，我们通过删除对 ClickHouse、Kafka 和 Zookeeper 的依赖来推出了精简版。我们将精简版作为默认的标准版本，并将完整版重命名为 FeatBit 专业版。

* 标准版非常适合小型企业，而专业版则非常适合中大型企业。
* 标准版和专业版都具有**可扩展和快速**的特点，并且**具有相同的功能**。
* 标准版是一个更**轻量级**的选择，只依赖于 Redis 和 MongoDB。
* 专业版**更为复杂**，依赖于 Redis、MongoDB、Kafka、Zookeeper 和 ClickHouse。
* Redis 是标准版的消息队列首选，而 Kafka 用于专业版。
* MongoDB 是标准版的数据分析工具首选，而 ClickHouse 用于专业版。