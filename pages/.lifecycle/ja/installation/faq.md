# FAQ

### Dockerコンテナのポート競合問題の解決方法

**Q:** `docker-compose up -d`を実行する際のDockerコンテナのポート競合問題を解決する方法は？

**A:** 単にdocker-compose.yml内のコンテナポートを変更する必要があります。

たとえば、すでにホストマシンのポート6379を使用しているRedisコンテナがある場合、`docker-compose up -d`を使用してシステムを起動しようとすると、次のようなDockerデーモンからのポート競合エラーが表示されることがあります。

![](./assets/faq/001.webp)

この問題を解決するには、**docker-compose.yml**に移動し、Redisサービスを見つけて、バインディングポートを6379以外の適切な値に変更します。

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
    # バインディングポートを6380に変更します
    - "6380:6379"
  volumes:
    - redis:/data
```

### FeatBitポータルを公開アクセス可能にする方法

デフォルトの設定では、FeatBitのポータルは、docker composeを実行したローカルマシンからのみアクセス可能です。

UIを他のマシンやインターネットからアクセス可能にするには、実行しているマシンに公開IPまたはドメイン名が必要です。さらに、APIサービスと評価サービスがUIサービスとは異なるマシンで実行されている場合は、それらに対しても公開IPアドレスまたはドメイン名が必要になる場合があります。次に、docker-composeファイルで**API\_URL**と**EVALUATION\_URL**の正しい値を設定します。詳細な説明については、FeatBitの[標準版](../tech-stack/architecture)および[プロフェッショナル版](../tech-stack/architecture-professional)のアーキテクチャドキュメントを参照してください。

```yaml
# docker-compose.yml
ui:
  image: featbit/featbit-ui:latest
  container_name: ui
  environment:
    # 例: 192.168.56.1:5000
    - API_URL=http://[APIサーバーのIPまたはドメインで置き換え]
    # チュートリアル用なのでそのままにしておきます
    - DEMO_URL=https://featbit-samples.vercel.app
    # 例: 192.168.56.1:5100
    - EVALUATION_URL=http://[評価サーバーのIPまたはドメインで置き換え]
  depends_on:
    - api-docs-server
  ports:
    - "8081:80"
  networks:
    - featbit-network
```

### Azure Cosmos DBを使用したFeatBitの利用方法

Cosmos DBでは、ソートされるフィールドに常にインデックスが必要です。Cosmos DBを使用するためには、これらのインデックスを手動で作成する必要があります。以下はそれらを作成するためのスクリプトです。

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