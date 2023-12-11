# FAQ

**REST API エンドポイントの取得方法**

1. **はじめに** ページに移動します
2. フィーチャーフラグを作成するか、既存のフラグを選択して次に進みます
3. **SDK Configs** セクションから **Open API エンドポイント** をコピーします
   
1. **はじめに** ページに移動します
2. フィーチャーフラグを作成するか、既存のフラグを選択して次に進みます
3. **SDK Configs** セクションから **Open API エンドポイント** をコピーします
   
![](/assets/faq/001.png)

## REST API ドキュメントの確認方法

REST API ドキュメントを確認する方法は2つあります

1. デモサイトで確認できます：[https://featbit-tio-eu-api.azurewebsites.net/docs/index.html](https://featbit-tio-eu-api.azurewebsites.net/docs/index.html)
2. オンプレミスで FeatBit を実行している場合は、**OPEN API エンドポイント** を見つけて接尾辞 **/docs/index.html** を追加します

![](/assets/faq/002.png)

例：上記の例では、**http://localhost:5000/docs/index.html** となります。

## フィーチャーフラグの定義

フィーチャーフラグは FeatBit の主要なエンティティであり、以下のドキュメントでその定義が説明されています。

### フィーチャーフラグの構造

フィーチャーフラグ API を使用すると、パーセンテージの展開、特定のコンテキストへのターゲット指定、あるいは機能をプログラムでトグルすることが可能です。フィーチャーフラグの表現を見ることで、これらのタスクのどれを実行するかがわかります。

```json
{
  "envId": "a244b0fe-63ff-49e8-a949-e113383ba3e7",
  "name": "enable access token",
  "description": "This flag manipulate the access token feature",
  "key": "enable-access-token",
  "variationType": "boolean",
  "variations": [
    {
      "id": "73590b69-00e2-4ea0-99b3-67de155f0d90",
      "value": "true"
    },
    {
      "id": "986379ec-3d4c-44fe-83db-2ea607db0cab",
      "value": "false"
    }
  ],
  "targetUsers": [
    {
      "keyIds": ["user1", "user2"],
      "variationId": "73590b69-00e2-4ea0-99b3-67de155f0d90"
    },
    {
      "keyIds": ["user3"],
      "variationId": "986379ec-3d4c-44fe-83db-2ea607db0cab"
    }
  ],
  "rules": [
    {
      "id": "aa1641dc-6e20-44ff-8f60-afe5c5e7c447",
      "name": "Rule 1",
      "dispatchKey": null,
      "includedInExpt": false,
      "conditions": [
        {
          "property": "keyId",
          "op": "IsOneOf",
          "value": "[\"user10\",\"user11\",\"user12\"]"
        }
      ],
      "variations": [
        {
          "id": "73590b69-00e2-4ea0-99b3-67de155f0d90",
          "rollout": [0, 1],
          "exptRollout": 1
        }
      ]
    }
  ],
  "isEnabled": false,
  "disabledVariationId": "986379ec-3d4c-44fe-83db-2ea607db0cab",
  "fallthrough": {
    "dispatchKey": null,
    "includedInExpt": true,
    "variations": [
      {
        "id": "986379ec-3d4c-44fe-83db-2ea607db0cab",
        "rollout": [0, 1],
        "exptRollout": 1
      }
    ]
  },
  "exptIncludeAllTargets": true,
  "tags": [],
  "isArchived": false,
  "disabledVariation": {
    "id": "986379ec-3d4c-44fe-83db-2ea607db0cab",
    "value": "false"
  },
  "creatorId": "f7c637ac-fc8c-4f55-9238-cedf0908df35",
  "updatorId": "f7c637ac-fc8c-4f55-9238-cedf0908df35",
  "createdAt": "2023-03-20T19:07:50.217Z",
  "updatedAt": "2023-03-20T19:09:11.32Z",
  "id": "808d5b7e-e463-489f-b660-afcb013b434b"
}
```