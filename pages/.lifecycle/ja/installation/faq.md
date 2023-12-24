# FAQ

### Dockerコンテナのポート競合問題を解決する方法

**Q:** `docker compose up -d`を実行した時にDockerコンテナのポート競合問題が発生した場合、どうすれば解決できますか？

**A:** docker-compose.ymlのコンテナポートを変更するだけです。

例えば、ホストマシンのポート6379を使用しているRedisコンテナが既に存在する場合、`docker-compose up -d`を実行してシステムを起動しようとすると、Dockerデーモンからポート競合エラーが以下のように表示されます。

![](./assets/faq/001.webp)

この問題を解決するには、**docker-compose.yml**に移動し、Redisサービスを探して、バインドポートを6379以外の値に変更します。

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
    # バインドポートを6380に変更
    - "6380:6379"
  volumes:
    - redis:/data
```

### FeatBitポータルを公開する方法

デフォルトの設定では、FeatBitのポータルはdocker composeを実行したローカルマシンからのみアクセス可能です。

UIを他のマシンやインターネットからアクセス可能にするためには、UIが実行されているマシンのパブリックIPまたはドメイン名が必要です。また、APIサービスや評価サービスがUIサービスとは異なるマシンで実行されている場合、それらにもパブリックIPアドレスやドメイン名が必要になることがあります。次に、docker-composeファイル内の**API_URL**と**EVALUATION_URL**に適切な値を設定してください。FeatBitの全サービスに関する詳細な説明は、[標準版アーキテクチャドキュメント](../tech-stack/architecture)と[プロ版アーキテクチャドキュメント](../tech-stack/architecture-professional)をご覧ください。

```yaml
# docker-compose.yml
ui:
  image: featbit/featbit-ui:latest
  container_name: ui
  environment:
    # 例: 192.168.56.1:5000
    - API_URL=http://[APIサーバーのIPまたはドメインに置き換えてください]
    # このままにしてください、これはチュートリアル用です
    - DEMO_URL=https://featbit-samples.vercel.app
    # 例: 192.168.56.1:5100
    - EVALUATION_URL=http://[評価サーバーのIPまたはドメインに置き換えてください]
  depends_on:
    - api-docs-server
  ports:
    - "8081:80"
  networks:
    - featbit-network
```

### Azure Cosmos DBでFeatBitを使用する

Cosmos DBでは、ソートされるフィールドには常にインデックスが必要です。Cosmos DBでFeatBitを使用するには、これらのインデックスを手動で作成する必要があります。以下はインデックスを作成するスクリプトです：

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

#### 参考文献

* [https://learn.microsoft.com/en-us/azure/cosmos-db/mongodb/error-codes-solutions](https://learn.microsoft.com/en-us/azure/cosmos-db/mongodb/error-codes-solutions)
* [https://www.mongodb.com/community/forums/t/sort-in-cosmosdb-mongo-apis-mandates-indexing/115529](https://www.mongodb.com/community/forums/t/sort-in-cosmosdb-mongo-apis-mandates-indexing/115529)

