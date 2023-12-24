# SDK

使用 SDK 是理解如何通过功能标志交付、控制和试验软件的基本技能。

我们官方提供的 SDK 是您开始使用 Feature Flag 的最佳选择。它也是您实现 Feature Flag 最佳实践的最佳选择。所有的 SDK 都考虑以下最佳实践：

1. **本地缓存**，如果网络不可用，SDK 将使用本地缓存获取功能标志的评估结果。
2. **本地缓存更新**，如果网络可用，SDK 将使用最新的功能标志评估结果更新本地缓存。
3. **实时更新**，SDK 将实时从服务器接收最新的功能标志评估结果。
4. **高性能**，SDK 不会影响您的应用程序性能。
5. **兼容性**，SDK 将与旧版本的 SDK 兼容。您可以升级 SDK 而不会对您的应用程序产生任何影响。
6. **服务器端评估**，服务器端 SDK 将在服务器端评估功能标志。因此，您无需担心功能标志的网络延迟和安全性。
7. **客户端评估**，客户端 SDK 将从服务器检索最终结果，因此您不必担心功能标志对性能的影响。
8. **自定义事件和功能标志见解**，SDK 将向服务器发送自定义事件和功能标志见解。因此，您可以获得功能标志和自定义事件的见解。
9. **功能实验的自定义事件**，SDK 将向服务器发送自定义事件。因此，您可以使用自定义事件进行功能实验。
10. **重试机制**，如果网络不可用，SDK 将自动重试连接服务器。
11. **功能标志和评估更新侦听器**，SDK 将在功能标志或评估结果更新时通知您。

要开始使用我们的 SDK，我们提供两种方式：

- 按照门户中的指南快速在项目中实现 SDK。您可以在[此处](../getting-started/connect-an-sdk)阅读快速入门指南。
- 阅读 SDK 在 GitHub 上的 README 文件，手动在项目中实现 SDK。

## 手动连接 SDK

我们提供了各种客户端、服务器端和移动 SDK 供您选择。您可以选择您擅长的语言来加速完成快速入门。

### Javascript

我们提供了客户端 [Javascript/Typescript SDK](https://github.com/featbit/featbit-js-client-sdk)。我们还为 [React](https://github.com/featbit/featbit-samples/tree/main/samples/dino-game/interactive-demo-react) 和 [Vue](https://github.com/featbit/featbit-samples/tree/main/samples/dino-game/interactive-demo-vue) 提供了“恐龙游戏”示例。此 SDK 与 Typescript、React、Vue、Angular 等完美配合。

SDK 的 GitHub 存储库包含了如何使用它的完整教程。它还提供了一个示例项目供您试用。

### .NET

我们提供了[服务器端 .NET SDK](https://github.com/featbit/featbit-dotnet-sdk)供您使用。此 SDK 可以在您的控制台应用程序或 ASP.NET Core 应用程序中使用。

它也适用于前端应用程序，如 WPF、WinForm、MAUI 等。但我们不建议您在移动应用程序中使用它，因为它比真正的移动 SDK 消耗更多的电量。

SDK 的 GitHub 存储库包含了如何使用它的完整教程。它还提供了一个示例项目供您试用。

### Java

我们提供了[Java SDK](https://github.com/featbit/featbit-java-sdk)供您使用。此 SDK 可以在您的控制台应用程序或 Spring Boot 应用程序中使用。

SDK 的 GitHub 存储库包含了如何使用它的完整教程。它还提供了一个示例项目供您试用。

### Python

我们提供了[Python SDK](https://github.com/featbit/featbit-python-sdk)。SDK 的 GitHub 存储库包含了如何使用它的完整教程。它还提供了一个示例项目供您试用。

### Go

我们提供了[Go SDK](https://github.com/featbit/featbit-go-sdk)。SDK 的 GitHub 存储库包含了如何使用它的完整教程。它还提供了一个示例项目供您试用。


### REST API 和 WebSocket

我们不断致力于扩展我们的平台支持。但是，您所面向的特定平台可能目前没有可用的 SDK。在这种情况下，我们提供两种选择：

- 使用我们的 REST API 获取功能标志和评估结果。请参阅[使用 REST API 进行评估](retrieve-feature-flags-with-api)文档。 
- 使用我们的 WebSocket 接口获取功能标志的实时更新和功能标志的评估结果。请加入我们的[Slack 频道](https://join.slack.com/t/featbit/shared_invite/zt-1ew5e2vbb-x6Apan1xZOaYMnFzqZkGNQ)以获取有关此功能的更多信息。




我们积极鼓励并欢迎开发人员的贡献，他们可以通过创建缺失的 SDK 来帮助我们弥合差距。如果您成功开发了符合我们标准的 SDK，并且有兴趣进行合作，我们将很高兴将您的工作作为我们社区 SDK 之一。