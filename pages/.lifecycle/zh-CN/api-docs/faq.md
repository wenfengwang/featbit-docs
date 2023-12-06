# 常见问题解答

**如何获取REST API端点**

1. 转到**开始**页面
2. 创建一个功能标志或选择一个现有的标志，然后点击下一步
3. 从**SDK配置**部分复制**开放API端点**

![](/assets/faq/001.png)

## 如何查看REST API文档

有两种方法可以查看REST API文档

1. 您可以在演示站点上查看：[https://featbit-tio-eu-api.azurewebsites.net/docs/index.html](https://featbit-tio-eu-api.azurewebsites.net/docs/index.html)
2. 如果您正在运行本地的FeatBit，请找到OPEN API端点并添加后缀**/docs/index.html**

![](/assets/faq/002.png)

例如：在上面的示例中，应该是**http://localhost:5000/docs/index.html**。

## 功能标志定义

功能标志是FeatBit的主要实体，下面的文档解释了它的定义。

### 功能标志的结构

功能标志API允许您控制百分比发布、目标特定上下文，甚至以编程方式切换功能。通过查看功能标志的表示形式，我们可以了解如何完成任何这些任务。

```json
{
  "envId": "a244b0fe-63ff-49e8-a949-e113383ba3e7",
  "name": "启用访问令牌",
  "description": "此标志操作访问令牌功能",
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
      "name": "规则1",
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
  "creatorId": "f759bac2-1fca-4fc5-b0d6-301a30549612",
  "updatorId": "f759bac2-1fca-4fc5-b0d6-301a30549612",
  "createdAt": "2023-03-20T19:07:50.217Z",
  "updatedAt": "2023-03-20T19:09:11.32Z",
  "id": "808d5b7e-e463-489f-b660-afcb013b434b"
}
```