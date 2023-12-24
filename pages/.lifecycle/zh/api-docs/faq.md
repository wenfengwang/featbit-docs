# 常见问题解答

**如何获取 REST API 端点**

1. 转到 **Get Started** 页面
2. 创建一个特性标志或选择一个现有的，然后点击下一步
3. 从 **SDK Configs** 部分复制 **Open API Endpoint**

![](/assets/faq/001.png)

## 如何查看 REST API 文档

您有两种方式可以查看 REST API 文档

1. 您可以在演示站点上查看： [https://featbit-tio-eu-api.azurewebsites.net/docs/index.html](https://featbit-tio-eu-api.azurewebsites.net/docs/index.html)
2. 如果您是在本地部署 FeatBit，请找到 OPEN API 端点并添加后缀 **/docs/index.html**

![](/assets/faq/002.png)

例如：在上面的例子中，它应该是 **http://localhost:5000/docs/index.html**。

## 特性标志定义

特性标志是 FeatBit 的主要实体，以下文档解释了其定义。

### 特性标志解剖

特性标志 API 允许您控制百分比滚动发布、针对特定上下文进行定位，或者甚至以编程方式关闭一个特性。通过查看特性标志的表示，我们可以了解如何执行这些任务。

```json
{
  "envId": "a244b0fe-63ff-49e8-a949-e113383ba3e7",
  "name": "enable access token",
  "description": "This flag manipulates the access token feature",
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

