# SDK

使用 SDK 是理解如何通过特性标志（Feature Flags）交付、控制和实验软件的一项基本技能。

我们官方提供的 SDK 是您开始使用 Feature Flag 的最佳选择。它也是您实施 Feature Flag 最佳实践的最佳选择。所有 SDK 都遵循以下最佳实践：

1. **本地缓存**，如果网络不可用，SDK 将使用本地缓存来获取特性标志的评估结果。
2. **本地缓存更新**，如果网络可用，SDK 将用最新的特性标志评估结果更新本地缓存。
3. **实时更新**，SDK 将实时接收来自服务器的最新特性标志评估结果。
4. **高性能**，SDK 不会影响您应用程序的性能。
5. **兼容性**，SDK 将与旧版本 SDK 兼容。您可以升级 SDK 而不会对您的应用程序产生任何影响。
6. **服务器端评估**，服务器端 SDK 将在服务器端评估特性标志。因此，您无需担心特性标志的网络延迟和安全性。
7. **客户端评估**，客户端 SDK 将从服务器检索最终结果，所以您不必担心特性标志对性能的影响。
8. **自定义事件 & 特性标志洞察**，SDK 将自定义事件和特性标志洞察发送到服务器。因此，您可以获得关于特性标志和自定义事件的洞察。
9. **特性实验的自定义事件**，SDK 将自定义事件发送到服务器。因此，您可以使用自定义事件进行特性实验。
10. **重试机制**，如果网络不可用，SDK 将自动尝试重新连接服务器。
11. **特性标志 & 评估更新监听器**，当特性标志或评估结果更新时，SDK 将通知您。

要开始使用我们的 SDK，我们提供两种方式：

- 按照门户中的指南快速在您的项目中实施 SDK。您可以在[这里](../getting-started/connect-an-sdk)阅读快速入门指南。
- 阅读 GitHub 上 SDK 的 README 文件，手动在您的项目中实施 SDK。

## 手动连接 SDK

我们提供多种客户端、服务器端和移动 SDK 供您选择。您可以选择您擅长的语言来加速完成快速入门。

### JavaScript

我们提供客户端 [JavaScript/TypeScript SDK](https://github.com/featbit/featbit-js-client-sdk)。我们还为 [React](https://github.com/featbit/featbit-samples/tree/main/samples/dino-game/interactive-demo-react) 和 [Vue](https://github.com/featbit/featbit-samples/tree/main/samples/dino-game/interactive-demo-vue) 提供了“恐龙游戏”示例。此 SDK 可与 TypeScript、React、Vue、Angular 等完美配合。

SDK 的 GitHub 仓库包含了如何使用它的完整教程。它还提供了一个示例项目供您尝试。

### .NET

我们提供 [服务器端 .NET SDK](https://github.com/featbit/featbit-dotnet-sdk) 供您使用。此 SDK 可以在您的控制台应用或 ASP.NET Core 应用中使用。

它也可以用于前端应用程序，如 WPF、WinForm、MAUI 等。但我们不建议您在移动应用中使用它，因为它比专为移动应用设计的 SDK 更耗电。

SDK 的 GitHub 仓库包含了如何使用它的完整教程。它还提供了一个示例项目供您尝试。

### Java

我们提供 [Java SDK](https://github.com/featbit/featbit-java-sdk) 供您使用。此 SDK 可以在您的控制台应用或 Spring Boot 应用中使用。

SDK 的 GitHub 仓库包含了如何使用它的完整教程。它还提供了一个示例项目供您尝试。

### Python

我们提供 [Python SDK](https://github.com/featbit/featbit-python-sdk)。SDK 的 GitHub 仓库包含了如何使用它的完整教程。它还提供了一个示例项目供您尝试。

### Go

我们提供 [Go SDK](https://github.com/featbit/featbit-go-sdk)。SDK 的 GitHub 仓库包含了如何使用它的完整教程。它还提供了一个示例项目供您尝试。


### REST API 和 WebSocket

我们持续致力于扩展我们的平台支持。然而，您所针对的特定平台可能目前没有可用的 SDK。在这种情况下，我们提供两种替代方案：

- 使用我们的 REST API 来获取特性标志和评估结果。请参阅文档[通过 REST API 进行评估](retrieve-feature-flags-with-api)。
- 使用我们的 WebSocket 接口来实时获取特性标志更新和特性标志的评估结果。请加入我们的 [Slack 频道](https://join.slack.com/t/featbit/shared_invite/zt-1ew5e2vbb-x6Apan1xZOaYMnFzqZkGNQ) 获取更多关于此功能的信息。




我们积极鼓励并欢迎开发者的贡献，他们可以帮助我们通过创建缺失的 SDK 来弥合差距。如果您成功开发了一个符合我们标准的 SDK，并且有兴趣合作，我们会很高兴将您的作品作为我们社区 SDK 的一部分。