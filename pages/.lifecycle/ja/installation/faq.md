# よくある質問

### Dockerコンテナーポートの競合問題の解決方法

**Q:** `docker compose up -d`を実行するときに、Dockerコンテナーポートの競合問題をどのように解決すればよいですか？

**A:** docker-compose.yml内のコンテナーポートを変更する必要があります。

例えば、ホストマシンのポート6379を使用しているRedisコンテナがすでにある場合、`docker-compose up -d`でシステムを起動しようとすると、次のようなDockerデーモンからのポート競合エラーが表示されます

![](./assets/faq/001.webp)

この問題を解決するには、**docker-compose.yml**に移動し、Redisサービスを見つけて、6379以外のバインディングポートに変更します。

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
    # バインディングポートを6380に変更
    - "6380:6379"
  volumes:
    - redis:/data
```

### FeatBitポータルを一般公開可能にする方法

デフォルトの構成では、FeatBitのポータルはdocker composeを実行しているローカルマシンからのみアクセス可能です。

UIを他のマシンやインターネットからアクセス可能にするには、実行中のマシンに公開IPまたはドメイン名が必要です。また、APIおよび評価サービスがUIサービスとは異なるマシンで実行されている場合は、それらのためにも公開IPアドレスまたはドメイン名が必要になります。その後、docker-composeファイルで**API\_URL**と**EVALUATION\_URL**の正しい値を設定します。FeatBitのすべてのサービスについての詳しい説明については、[標準版](../tech-stack/architecture)および[プロフェッショナル版](../tech-stack/architecture-professional)のアーキテクチャドキュメントをご確認ください。

```yaml
# docker-compose.yml
ui:
  image: featbit/featbit-ui:latest
  container_name: ui
  environment:
    # 例: 192.168.56.1:5000
    - API_URL=http://[APIサーバーのIPまたはドメインで置き換え]
    # このままにしておいてください。これはチュートリアル用です
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

### Azure Cosmos DBを使用したFeatBitの利用

Cosmos DBでは常にソートされたフィールドにインデックスが必要です。Cosmos DBをFeatBitと共に使用するには、これらのインデックスを手動で作成する必要があります。以下はそれらを作成するためのスクリプトです:

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