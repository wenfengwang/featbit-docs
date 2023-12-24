# 常见问题

### 如何解决docker容器端口冲突问题

**问：** 当我运行 `docker compose up -d` 时，如何解决docker容器端口冲突问题？

**答：** 您只需要在 docker-compose.yml 中更改容器的端口。

例如，如果您已经有一个使用主机机器端口 6379 的 Redis 容器，当您尝试使用 `docker-compose up -d` 启动我们的系统时，您可能会从docker守护程序看到端口冲突错误，如下所示

![](./assets/faq/001.webp)

要解决这个问题，请转到 **docker-compose.yml**，找到 Redis 服务并将其绑定端口更改为除 6379 之外的其他端口。

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
    # 将绑定端口更改为 6380
    - "6380:6379"
  volumes:
    - redis:/data
```

### 如何使 FeatBit 门户可公开访问

使用默认配置时，FeatBit的门户只能从运行docker compose的本地机器访问。

要使UI能够从其他机器甚至是Internet访问，您需要运行UI的机器有一个公共IP或域名。此外，如果API和评估服务运行在与UI服务不同的机器上，您可能还需要它们的公共IP地址或域名。然后，在docker-compose文件中设置**API_URL**和**EVALUATION_URL**的正确值。请查看我们的[标准版](../tech-stack/architecture)和[专业版](../tech-stack/architecture-professional)的架构文档，详细解释了FeatBit的所有服务。

```yaml
# docker-compose.yml
ui:
  image: featbit/featbit-ui:latest
  container_name: ui
  environment:
    # 例如：192.168.56.1:5000
    - API_URL=http://[REPLACE_WITH_THE_API_SERVER_IP_OR_DOMAIN]
    # 保持不变，这是用于教程的
    - DEMO_URL=https://featbit-samples.vercel.app
    # 例如：192.168.56.1:5100
    - EVALUATION_URL=http://[REPLACE_WITH_THE_EVALUATION_SERVER_IP_OR_DOMAIN]
  depends_on:
    - api-docs-server
  ports:
    - "8081:80"
  networks:
    - featbit-network
```

### 如何在Azure Cosmos DB中使用FeatBit

Cosmos DB始终需要为要排序的字段创建索引。要在Cosmos DB中使用FeatBit，您需要手动创建这些索引。下面是创建它们的脚本：

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

#### 参考

* [https://learn.microsoft.com/en-us/azure/cosmos-db/mongodb/error-codes-solutions](https://learn.microsoft.com/en-us/azure/cosmos-db/mongodb/error-codes-solutions)
* [https://www.mongodb.com/community/forums/t/sort-in-cosmosdb-mongo-apis-mandates-indexing/115529](https://www.mongodb.com/community/forums/t/sort-in-cosmosdb-mongo-apis-mandates-indexing/115529)