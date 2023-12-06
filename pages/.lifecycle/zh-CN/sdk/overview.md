# SDK

使用SDK是了解如何通过功能标志交付、控制和实验软件的基本技能。

我们提供的官方SDK是您入门功能标志的最佳选择。它也是您实施功能标志最佳实践的最佳选择。所有SDK都考虑以下最佳实践：

1. **本地缓存**，如果网络不可用，SDK将使用本地缓存获取功能标志评估结果。
2. **本地缓存更新**，如果网络可用，SDK将使用最新的功能标志评估结果更新本地缓存。
3. **实时更新**，SDK将从服务器实时接收最新的功能标志评估结果。
4. **高性能**，SDK不会影响您的应用程序性能。
5. **兼容性**，SDK将与旧版SDK兼容。您可以升级SDK而不会对您的应用程序产生任何影响。
6. **服务器端评估**，服务器端SDK将在服务器端评估功能标志。因此，您不需要担心功能标志的网络延迟和安全性。
7. **客户端评估**，客户端SDK将从服务器检索最终结果，因此您不必担心功能标志的性能影响。
8. **自定义事件和功能标志洞察**，SDK将发送自定义事件和功能标志洞察到服务器。因此，您可以获得功能标志和自定义事件的洞察。
9. **用于功能实验的自定义事件**，SDK将发送自定义事件到服务器。因此，您可以使用自定义事件进行功能实验。
10. **重试机制**，如果网络不可用，SDK将自动重试连接到服务器。
11. **功能标志和评估更新监听器**，当功能标志或评估结果更新时，SDK将通知您。

要开始使用我们的SDK，我们提供了两种方式：

- 在门户网站中按照指南快速在您的项目中实现SDK。您可以在此处阅读快速入门指南 [here](../getting-started/connect-an-sdk)。
- 在GitHub上阅读SDK的README文件，以在您的项目中手动实现SDK。

## 手动连接SDK

我们提供了各种可以选择的客户端、服务器端和移动SDK。您可以选择您擅长的语言来加快完成入门。

### Javascript

我们提供了客户端的[Javascript/Typescript SDK](https://github.com/featbit/featbit-js-client-sdk)。我们还提供了[Dino Game](https://github.com/featbit/featbit-samples/tree/main/samples/dino-game/interactive-demo-react)的样例，适用于[React](https://github.com/featbit/featbit-samples/tree/main/samples/dino-game/interactive-demo-vue)和[Vue](https://github.com/featbit/featbit-samples/tree/main/samples/dino-game/interactive-demo-react)。此SDK与Typescript、React、Vue、Angular等完美配合使用。

SDK的GitHub存储库包含了使用它的完整教程。它还提供了一个样例项目供您尝试。

### .NET

我们提供了适用于服务器端的[.NET SDK](https://github.com/featbit/featbit-dotnet-sdk)供您使用。该SDK可用于控制台应用程序或ASP.NET Core应用程序。

它也适用于前端应用程序，如WPF、WinForm、MAUI等。但是，我们不建议您在移动应用程序中使用它，因为它比真正的移动SDK消耗更多的电池电量。

SDK的GitHub存储库包含了使用它的完整教程。它还提供了一个样例项目供您尝试。

### Java

我们提供了[Java SDK](https://github.com/featbit/featbit-java-sdk)供您使用。该SDK可用于控制台应用程序或Spring Boot应用程序。

SDK的GitHub存储库包含了使用它的完整教程。它还提供了一个样例项目供您尝试。

### Python

我们提供了[Python SDK](https://github.com/featbit/featbit-python-sdk)。SDK的GitHub存储库包含了使用它的完整教程。它还提供了一个样例项目供您尝试。

### Go

我们提供了[Go SDK](https://github.com/featbit/featbit-go-sdk)。SDK的GitHub存储库包含了使用它的完整教程。它还提供了一个样例项目供您尝试。

### REST APIs和WebSocket

我们不断致力于扩大我们的平台支持。然而，您所针对的特定平台可能目前没有可用的SDK。在这种情况下，我们提供两种替代方案：

- 使用我们的REST API获取功能标志和评估结果。请参阅[使用REST API进行评估](retrieve-feature-flags-with-api)文档。
- 使用我们的WebSocket接口获取实时的功能标志更新和功能标志的评估结果。请加入我们的[Slack频道](https://join.slack.com/t/featbit/shared_invite/zt-1ew5e2vbb-x6Apan1xZOaYMnFzqZkGNQ)以了解更多有关此功能的信息。

我们积极鼓励和欢迎开发人员为我们创建缺失的SDK以弥合差距。如果您成功开发了一个符合我们标准的SDK，并有兴趣合作，我们将非常高兴将您的作品作为我们社区SDK之一。