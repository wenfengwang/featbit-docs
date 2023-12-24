# 用户组

IAM 用户组是 IAM 成员的集合。用户组可以让您为多个成员指定权限，从而更轻松地管理这些成员的权限。例如，您可以创建一个名为 _管理员_ 的用户组，并为该用户组授予典型的管理员权限。该用户组中的任何成员都会自动拥有 _管理员_ 用户组的权限。

如果新用户加入您的组织并需要管理员权限，您可以通过将该用户添加到 _管理员_ 用户组来分配相应的权限。如果组织内的某个人更换了工作岗位，您可以将其从旧用户组中移除，并将其添加到相应的新用户组中，而不是编辑该用户的权限。

您可以将策略附加到用户组，以便用户组中的所有用户都获得该策略的权限。以下是用户组的一些重要特点：

* 一个用户组可以包含多个用户，而一个用户可以属于多个用户组。
* 用户组不能嵌套；它们只能包含用户，而不能包含其他用户组。
* 在 FeatBit 帐户中没有默认组自动包含所有用户。如果您需要这样的组，必须创建并为每个新用户分配。
* FeatBit 帐户中的 IAM 资源数量和大小（例如组的数量，以及用户可以成为成员的组的数量）是受限制的。

## 创建用户组

1\. 转到 IAM 部分下的 **用户组** 页面

2\. 单击 **添加** 按钮

![](../iam/assets/groups/001.webp)

3\. 输入用户组的名称和描述（可选）

4\. 单击 **保存** 按钮

![](../iam/assets/groups/002.webp)

5\. 在用户组列表中点击刚刚创建的用户组，进入用户组详情页面。

6\. 您将会看到用户组页面

![](../iam/assets/groups/003.webp)

## 用户组详情页面

用户组详情页面由 4 部分组成：

1. 用户组的 **名称** 和 **说明**
2. 用户组的 **资源名称**，这将在 IAM 的未来功能中使用
3. **团队** 选项卡，显示此用户组中包含的成员列表
4. **策略** 选项卡，显示分配给此用户组的权限

## 用户组列表

在用户组列表中，您可以按名称筛选用户组

![](../iam/assets/groups/004.webp)

## 将成员添加到用户组

1\. 进入用户组详情页面，切换到 **团队** 选项卡

2\. 将选择器设置为 `All`，您将看到组织中的所有成员

![](../iam/assets/groups/005.webp)

3\. 找到要添加到用户组中的成员（您可以通过电子邮件进行筛选）。单击列表中成员项上的 **添加** 按钮。

![](../iam/assets/groups/006.webp)

4\. 将选择器从 `All` 更改为 `Contained by current group`。您只能看到包含在用户组中的成员。

![](../iam/assets/groups/007.webp)

5\. 如果要从用户组中移除成员，请单击 **移除** 按钮。

## 将权限策略附加到用户组

1\. 在用户组详情页面，切换到 **策略** 选项卡

2\. 将选择器设置为 `All`，您将看到所有策略

![](../iam/assets/groups/008.webp)

3\. 找到要附加到用户组的策略（您可以按策略名称进行筛选）。单击列表中策略项上的 **添加** 按钮。

![](../iam/assets/groups/009.webp)

4\. 将选择器从 `All` 更改为 `Attached to current group`。您只会看到附加到此用户组的策略。

![](../iam/assets/groups/010.webp)

5\. 如果要从用户组中移除策略，请单击 **移除** 按钮。