# 常见问题解答

### 如何解决docker容器端口冲突问题

**问：** 当我运行 `docker compose up -d` 时，如何解决docker容器端口冲突问题？

**答：** 您只需要在docker-compose.yml中更改容器端口。

例如，如果您已经有一个使用主机机器的端口6379的Redis容器，当您尝试使用 `docker-compose up -d` 启动我们的系统时，您会从docker的守护程序中看到端口冲突错误，如下所示

![](./assets/faq/001.webp)

要解决这个问题，进入 **docker-compose.yml**，找到Redis服务，并将其绑定端口更改为不同于6379的其他端口。

```yaml
# redis service
redis:
  image: bitnami/redis:6.2.7
  container_name: redis
  restart: on-failure
  environment:
    - ALLOW_EMPTY_PASSWORD=yes
  networks:
    - featbit-network
  ports:
    # 将绑定端口更改为6380
    - "6380:6379"
  volumes:
    - redis:/data
```

### 如何使FeatBit门户公开访问

默认情况下，FeatBit的门户只能从您运行docker compose的本机访问。

要使UI界面从其他机器甚至从互联网访问，您需要为其运行的机器获取公共IP或域名。此外，如果API和评估服务运行在与UI服务不同的机器上，您可能还需要为它们获取公共IP地址或域名。然后，在docker-compose文件中设置 **API\_URL** 和 **EVALUATION\_URL** 的正确值。请查看我们的架构文档[标准版](../tech-stack/architecture)和[专业版](../tech-stack/architecture-professional)以详细解释FeatBit的所有服务。

```yaml
# docker-compose.yml
ui:
  image: featbit/featbit-ui:latest
  container_name: ui
  environment:
    # 示例：192.168.56.1:5000
    - API_URL=http://[用实际的API服务器IP或域名替换]
    # 保持现状，这是为教程准备的
    - DEMO_URL=https://featbit-samples.vercel.app
    # 示例：192.168.56.1:5100
    - EVALUATION_URL=http://[用实际的评估服务器IP或域名替换]
  depends_on:
    - api-docs-server
  ports:
    - "8081:80"
  networks:
    - featbit-network
```

### 如何在Azure Cosmos DB中使用FeatBit

Cosmos DB始终对排序字段要求创建索引。要在Cosmos DB中使用FeatBit，您需要手动创建这些索引。以下是创建它们的脚本：

```javascript
const createdAtCollections = ["RelayProxies", "Projects", "AccessTokens", "Policies", "AuditLogs"];
createdAtCollections.forEach(collection => {
    db.getCollection(collection).createIndex(
        { "createdAt": -1 },
        { background: true }
    );
});
const updatedAtCollections = ["EndUsers", "FeatureFlags", "Segments"]
updatedAtCollections.forEach(collection => {
    db.getCollection(collection).createIndex(
        { "updatedAt": -1 },
        { background: true }
    );
});
```

#### 参考链接

* [https://learn.microsoft.com/en-us/azure/cosmos-db/mongodb/error-codes-solutions](https://learn.microsoft.com/en-us/azure/cosmos-db/mongodb/error-codes-solutions)
* [https://www.mongodb.com/community/forums/t/sort-in-cosmosdb-mongo-apis-mandates-indexing/115529](https://www.mongodb.com/community/forums/t/sort-in-cosmosdb-mongo-apis-mandates-indexing/115529)