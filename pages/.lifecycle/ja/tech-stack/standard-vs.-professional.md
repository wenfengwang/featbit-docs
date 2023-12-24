# Standard VS. Professional

以前、FeatBitは依存関係が多すぎてデプロイが困難でした。これらの依存関係の多くは小規模ビジネスには不要です。そこで、ClickHouse、Kafka、Zookeeperを取り除き、ライトバージョンを導入しました。このライトバージョンをデフォルトのStandardバージョンとし、フルバージョンをFeatBit Professionalと改名しました。

* Standardバージョンは小規模ビジネスに理想的で、Professionalバージョンは中規模から大規模ビジネスに理想的です。
* StandardバージョンとProfessionalバージョンはどちらも**スケーラブルで高速**であり、**同一の機能を持っています**。
* StandardバージョンはRedisとMongoDBのみに依存する、より**軽量**なオプションです。
* Professionalバージョンはより**ヘビー**で、Redis、MongoDB、Kafka、Zookeeper、およびClickHouseに依存しています。
* RedisはStandardバージョンのメッセージキューとして、KafkaはProfessionalバージョンで使用されます。
* MongoDBはStandardバージョンのデータ分析ツールとして選ばれ、ClickHouseはProfessionalバージョンで使用されます。

