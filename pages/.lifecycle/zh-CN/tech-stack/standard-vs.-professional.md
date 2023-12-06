# 标准版 vs 专业版

以前，部署FeatBit有些困难，因为它有太多的依赖项。其中许多对于小型企业来说并不必要。因此，我们通过移除对ClickHouse、Kafka和Zookeeper的依赖，引入了一个精简版本。我们将精简版作为默认的标准版本，并将完整版本更名为FeatBit专业版。

* 标准版适用于小型企业，而专业版适用于中型和大型企业。
* 标准版和专业版都是 **可扩展和快速** 的，**具有相同的功能**。
* 标准版是一种更 **轻量级** 的选择，只依赖于Redis和MongoDB。
* 专业版更 **重量级**，依赖于Redis、MongoDB、Kafka、Zookeeper和ClickHouse。
* 标准版选择Redis作为消息队列，而专业版选择Kafka。
* 标准版选择MongoDB作为数据分析工具，专业版选择ClickHouse。