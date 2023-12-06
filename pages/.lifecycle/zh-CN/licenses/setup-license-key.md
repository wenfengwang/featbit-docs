import { Callout } from 'nextra/components'

# 设置许可证密钥

<Callout type="info">
  此文章兼容 FeatBit 版本 3.0.0 及以上。
</Callout>

本指南说明了如何使用许可证密钥设置 FeatBit。

## 获取工作区 ID

在获取许可证密钥之前，你需要工作区 ID。请按照以下步骤操作：

1. 确保 FeatBit 正在运行，并假设 FeatBit 用户界面可通过 http://localhost:8081 访问。
2. 使用你的电子邮件和密码登录 FeatBit。对于默认设置，请使用：
   - 用户名：test@featbit.com
   - 密码：123456

3. 转到 http://localhost:8081/en/workspace，在 **License Settings** 部分，点击 **Copy** 按钮。
   
   ![](./assets/workspaceid.png)

## 获取免费试用许可证密钥

为了评估所有 FeatBit 功能，你可以从 [FeatBit 仪表盘](https://dashboard.featbit.co/account) 生成一个免费试用许可证密钥：

- 使用你的电子邮件创建一个账户，或通过 GitHub 登录。
- 在 **Account** 页面，点击 **Generate Trial License**。

  ![](./assets/request-trial-license1.png)
- 在弹出窗口中，输入你的公司名和工作区 ID，然后点击 **OK**。

  ![](./assets/request-trial-license2.png)
- 在许可证表中找到生成的许可证，并点击复制。

  ![](./assets/request-trial-license3.png)

## 获取商业许可证密钥

如果需要商业许可证密钥，请发送电子邮件至 [contact@featbit.co](mailto:contact@featbit.co)，或加入我们的 [Slack 频道](https://join.slack.com/t/featbit/shared_invite/zt-1ew5e2vbb-x6Apan1xZOaYMnFzqZkGNQ)，我们将尽快回复。
## 上传许可证密钥

现在返回到 http://localhost:8081/en/workspace，进入 **License Settings** 部分，输入之前获得的许可证密钥，然后点击 **Update**。

![](./assets/save_license_key.png)

保存后，将鼠标悬停在 Enterprise 按钮上，即可查看许可证详细信息，如下所示

![](./assets/check-license.png)