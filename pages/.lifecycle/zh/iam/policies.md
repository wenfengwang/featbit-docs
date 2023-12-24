# 策略

在 FeatBit 中，您可以通过创建策略并将其附加到 IAM 身份（用户、用户组）或 FeatBit 资源来管理访问。策略是 FeatBit 中的一个对象，当与标识或资源关联时，定义了它们的权限。当 IAM 成员发出请求时，FeatBit 会评估这些策略。策略中的权限决定请求是允许还是拒绝。

## 控制级别（资源类型）

FeatBit 策略现在支持三个控制级别（也称为资源类型）：

* **All**，用于控制成员（或成员组）对所有资源的访问权限，决定是否允许或拒绝。
* **General**，用于控制成员对 Account、IAM 和 Project 资源级别的访问权限。
* **Project**，用于控制成员对项目的访问权限。
* **Environment**，用于控制成员对所有环境的访问权限。

## 内置策略

FeatBit 提供了三个无法修改的内置策略。如果需要，您可以创建副本并根据需要进行修改。

![](../iam/assets/policies/001.webp)

## 添加策略

1\. 转到策略页面，单击“添加”按钮。

2\. 在“添加策略”抽屉中，输入新策略的名称和描述。然后单击 **“保存”** 进行创建。

3\. 新的项目将添加到策略列表中。您可以按名称筛选策略，以查找刚刚创建的策略。

4\. 单击刚刚创建的策略（或单击 **“详细信息”** 操作按钮），转到策略详细信息页面。

## 策略详细信息页面

策略详细信息页面由 6 个部分组成：

* 策略的名称和说明
* 策略类型（由系统生成）
* 资源名称
* 权限列表，可以添加、更新和删除策略的权限
* 团队，可以将此策略分配给成员或从成员中删除策略
* 组，可以将此策略分配给组或将其从组中删除。

## 添加权限

1\. 单击 `(+)` 图标，将出现一个新的空权限表单。

2\. 选择控制级别（资源类型）。如果要控制环境级别的访问权限，请选择 **`Environment`**。

3\. 选择要拒绝或允许访问的资源。

* 在资源选择器中，我们选择 project/explore：env/Dev。这意味着我们要分配访问权限的`product`环境属于`explore`项目。您可以选择多个资源，这里我们只选择一个。
* 在允许或拒绝选择器中，我们选择 `Allow`。
* 在操作选择器中，我们选择 `Access environments`。

4\. 点击 **保存**。您可以在策略中创建多个权限。

我们刚刚创建的权限允许拥有此权限的成员访问`explore`项目中`product`环境的所有资源，但这些成员不能修改资源。

每个策略可以添加多个权限。

## 删除权限

您可以通过单击权限列表中的 `Remove` 按钮来删除权限。

![](../iam/assets/policies/002.webp)

## 分配权限给成员

1\. 转到策略详细信息页面，切换到 **“团队”** 选项卡。

2\. 将选择器设置为 `All`，您将看到组织中的所有成员。

![](../iam/assets/policies/003.webp)

3\. 找到向其分配策略的成员。单击列表中成员项上的 **“添加”** 按钮。

4\. 将选择器从 `All` 更改为 `Members with current policy`。您只能看到具有当前策略的成员。

![](../iam/assets/policies/004.webp)

5\. 单击 **“删除”** 按钮以从策略中删除成员。

## 分配权限给组

1\. 进入策略详情页面，切换到 **“组”** 选项卡。

2\. 将选择器设置为 `All`，您将看到组织中的所有组。

![](../iam/assets/policies/005.webp)

3\. 找到将策略分配到的组。单击列表中组项上的 **“添加”** 按钮。

4\. 将选择器从 `All` 更改为 `Groups with current policy`。您只能看到具有当前策略的组。

![](../iam/assets/policies/006.webp)

5\. 单击 **“删除”** 按钮以从策略中删除组。