
# 软件开发套件

掌握SDK的使用是理解如何通过功能标志来交付、控制和测试软件的一项重要技能。

我们官方提供的SDK是您开始使用功能标志的最佳选择，同时也是实施功能标志最佳实践的理想选择。所有SDK都遵循以下最佳实践：

1. **本地缓存**，如果网络不可用，SDK将利用本地缓存获取功能标志的评估结果。
2. **本地缓存更新**：如果网络可用，SDK将使用最新的功能标志评估结果更新本地缓存。
3. **实时更新**，SDK将实时接收服务器的最新功能标志评估结果。
4. **高性能**：SDK不会影响您应用程序的性能。
5. **兼容性**：SDK将与旧版本SDK兼容。您可以无缝升级SDK，不会对您的应用产生任何影响。
6. **服务器端评估**：服务器端SDK将在服务器端评估功能标志。所以您无需担心功能标志的网络延迟和安全问题。
7. **客户端评估**：客户端SDK将从服务器检索最终结果，因此您不必担心功能标志对性能的影响。
8. **自定义事件与功能标志洞察**：SDK会将自定义事件和功能标志洞察发送到服务器，让您洞悉功能标志和自定义事件的情况。
9. **功能实验的自定义事件**：SDK会将自定义事件发送到服务器。因此，您可以利用这些自定义事件来进行功能实验。
10. **重试机制**，如果网络不可用，SDK会自动尝试重新连接服务器。
11. **功能标志**与评估更新监听器，SDK会在功能标志或评估结果更新时通知您。

要开始使用我们的SDK，我们提供两种方式：

- 按照门户网站中的指南快速在您的项目中实施SDK。您可以在[这里](../getting-started/connect-an-sdk)阅读快速启动指南。
- - 阅读GitHub上SDK的README文件，手动在您的项目中实现SDK。

## 手动连接SDK

我们提供多种客户端、服务器端和移动SDK供您选择。您可以选择自己熟悉的语言来加速完成快速启动。

### JavaScript

我们提供客户端[Javascript/Typescript SDK](https://github.com/featbit/featbit-js-client-sdk)。同时，我们还为[React](https://github.com/featbit/featbit-samples/tree/main/samples/dino-game/interactive-demo-react)和[Vue](https://github.com/featbit/featbit-samples/tree/main/samples/dino-game/interactive-demo-vue)提供了“恐龙游戏”示例。这个SDK与TypeScript、React、Vue、Angular等框架搭配使用效果极佳。

SDK的GitHub仓库中含有完整的使用教程，也提供了一个示例项目供您尝试。

### .NET

我们提供一个[server-side .NET SDK](https://github.com/featbit/featbit-dotnet-sdk)供您使用。这个SDK可以在您的控制台应用或ASP.NET Core应用中使用。

它也适用于WPF、WinForm、MAUI等前端应用程序。但我们不建议在移动应用程序中使用它，因为相比专用移动SDK，它会消耗更多电量。

SDK的GitHub仓库中含有完整的使用教程，也提供了一个示例项目供您尝试。

### Java

我们提供一个[Java SDK](https://github.com/featbit/featbit-java-sdk)供您使用。这个SDK可以在您的控制台应用或Spring Boot应用中使用。

SDK的GitHub仓库中含有完整的使用教程，也提供了一个示例项目供您尝试。

### Python

我们提供一个[Python SDK](https://github.com/featbit/featbit-python-sdk)。SDK的GitHub仓库中含有完整的使用教程，也提供了一个示例项目供您尝试。

### Go

我们提供一个[Go SDK](https://github.com/featbit/featbit-go-sdk)。SDK的GitHub仓库中含有完整的使用教程，也提供了一个示例项目供您尝试。

### REST API与WebSocket

我们持续致力于扩展我们的平台支持。然而，您目标的特定平台可能目前还没有可用的SDK。在这种情况下，我们提供两种替代方案：

- 使用我们的REST API来获取功能标志和评估结果。详情请参见[使用REST API进行评估的文档](retrieve-feature-flags-with-api)。
- - 使用我们的WebSocket接口来实时获取功能标志更新和功能标志的评估结果。请加入我们的[Slack频道](https://join.slack.com/t/featbit/shared_invite/zt-1ew5e2vbb-x6Apan1xZOaYMnFzqZkGNQ)以获取更多关于此功能的信息。

我们非常欢迎开发者贡献力量，帮助我们通过创建缺失的SDK来弥补差距。如果您成功开发出符合我们标准的SDK并感兴趣与我们合作，我们将非常荣幸地把您的作品作为社区SDK之一。
