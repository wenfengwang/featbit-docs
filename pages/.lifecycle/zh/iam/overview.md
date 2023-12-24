# 身份和访问管理（IAM）

FeatBit IAM 为您提供对 FeatBit 中的所有内容进行精确的访问控制，包括功能标志、项目、环境、指标和团队，因此您可以执行符合您确切工作流程需求的访问策略。通过自定义角色，您可以：

* 将生产环境锁定为一小组受信任的用户
* 允许团队成员控制仅供其团队使用的项目或环境上的功能标志（正在进行中）
* 在标志级别允许不同的权限，例如在实验标志和操作标志之间（正在进行中）
* 创建只有您选择的团队成员才能查看的私有项目。

我们的 IAM 系统受到 [AWS身份和访问管理（IAM）](https://aws.amazon.com/iam/) 的启发。如果您熟悉 IAM，就会发现有一些相似之处。每个团队成员必须至少拥有一个策略。

您可以为团队成员分配内置策略或一个或多个自定义策略，以授予他们所需的确切权限。

当您向 FeatBit 添加新成员时，将设置团队成员的初始策略。

唯一的例外是第一个团队成员，即默认用户。他的策略会自动被授予“所有者”权限，因为需要这些权限才能完全配置您的团队并添加更多团队成员。

您可以阅读下面的主题，了解如何为特定团队成员或一组成员设置权限。

* [团队](teams.md)
* [组](groups.md)
* [策略](policies.md)