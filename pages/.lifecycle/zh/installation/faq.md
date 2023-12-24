# 常见问题解答

### 如何解决 Docker 容器端口冲突问题

**Q：** 当我运行 `docker compose up -d` 时，如何解决 Docker 容器端口冲突问题？

**A：** 您只需要更改 docker-compose.yml 中的容器端口即可。

例如，如果您已经有一个 Redis 容器使用了主机的 6379 端口，当您尝试用 `docker-compose up -d` 启动我们的系统时，您可以看到 Docker 守护进程报告的端口冲突错误，如下图所示

![](./assets/faq/001.webp)

要解决这个问题，请转到 **docker-compose.yml**，找到 Redis 服务并将它的绑定端口改为 6379 以外的其他端口。

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

### 如何使 FeatBit 门户能够公开访问

使用默认配置，FeatBit 门户仅能从运行 Docker Compose 的本地机器上访问。

要使 UI 能够从其他机器甚至是互联网上访问，您需要为运行它的机器设置一个公共 IP 或域名。此外，如果 API 和评估服务不是在 UI 服务的同一台机器上运行，您可能还需要为它们设置公共 IP 地址或域名。然后，在 docker-compose 文件中设置 **API_URL** 和 **EVALUATION_URL** 的正确值。请查阅我们的[标准版](../tech-stack/architecture)和[专业版](../tech-stack/architecture-professional)架构文档，以详细了解 FeatBit 的所有服务。

```yaml
# docker-compose.yml
ui:
  image: featbit/featbit-ui:latest
  container_name: ui
  environment:
    # 例如：192.168.56.1:5000
    - API_URL=http://[REPLACE_WITH_THE_API_SERVER_IP_OR_DOMAIN]
    # 保持原样，这是为了教程
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

### 将 FeatBit 与 Azure Cosmos DB 一起使用

Cosmos DB 总是要求对排序字段建立索引。要将 FeatBit 与 Cosmos DB 一起使用，您需要手动创建这些索引。以下是创建索引的脚本：

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

#### 参考资料

* [https://learn.microsoft.com/en-us/azure/cosmos-db/mongodb/error-codes-solutions](https://learn.microsoft.com/en-us/azure/cosmos-db/mongodb/error-codes-solutions)
* [https://www.mongodb.com/community/forums/t/sort-in-cosmosdb-mongo-apis-mandates-indexing/115529](https://www.mongodb.com/community/forums/t/sort-in-cosmosdb-mongo-apis-mandates-indexing/115529)

