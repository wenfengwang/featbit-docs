
# 常见问题解答

### 如何解决 Docker 容器端口冲突问题

**问：**当我执行`docker-compose up -d`命令时，如何解决Docker容器端口冲突的问题？

**A:** 您只需更改 docker-compose.yml 文件中的容器端口设置。

例如，如果您已有一个Redis容器使用了宿主机的6379端口，当您尝试用 docker-compose up -d 启动我们的系统时，可能会看到 Docker 守护进程报告的端口冲突错误，如下所示：

![](./assets/faq/001.webp)

要解决这个问题，请打开 **docker-compose.yml** 文件，找到 Redis 服务并将其绑定的端口改为除了6379之外的其他端口。

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
    # change the binding port to 6380
    - "6380:6379"
  volumes:
    - redis:/data
```

### 如何让 FeatBit 门户能够公开访问

默认情况下，FeatBit 门户仅能在运行了 docker-compose 命令的本地计算机上访问。

为了使用户界面（UI）能从其他计算机甚至互联网上访问，您需要为运行该服务的计算机配置公共 IP 地址或域名。此外，如果 API 和评估服务不是在托管 UI 服务的同一台计算机上运行，您也可能需要为它们配置公共 IP 地址或域名。然后，在 docker-compose 文件中正确设置 **API\_URL** 和 **EVALUATION\_URL** 的值。请参考我们的[标准版](../tech-stack/architecture)和[专业版](../tech-stack/architecture-professional)架构文档，了解 FeatBit 所有服务的详细信息。

```yaml
# docker-compose.yml
ui:
  image: featbit/featbit-ui:latest
  container_name: ui
  environment:
    # example: 192.168.56.1:5000
    - API_URL=http://[REPLACE_WITH_THE_API_SERVER_IP_OR_DOMAIN]
    # keep it like this, this is for tutorial
    - DEMO_URL=https://featbit-samples.vercel.app
    # example: 192.168.56.1:5100
    - EVALUATION_URL=http://[REPLACE_WITH_THE_EVALUATION_SERVER_IP_OR_DOMAIN]
  depends_on:
    - api-docs-server
  ports:
    - "8081:80"
  networks:
    - featbit-network
```

### 如何将 FeatBit 与 Azure Cosmos DB 一起使用

Cosmos DB 要求对进行排序的字段建立索引。若要将 FeatBit 与 Cosmos DB 一起使用，您需要手动创建这些索引。以下是创建索引的脚本：

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

* [https://learn.microsoft.com/zh-cn/azure/cosmos-db/mongodb/error-codes-solutions](https://learn.microsoft.com/zh-cn/azure/cosmos-db/mongodb/error-codes-solutions)
* [https://www.mongodb.com/community/forums/t/sort-in-cosmosdb-mongo-apis-mandates-indexing/115529](https://www.mongodb.com/community/forums/t/sort-in-cosmosdb-mongo-apis-mandates-indexing/115529)
