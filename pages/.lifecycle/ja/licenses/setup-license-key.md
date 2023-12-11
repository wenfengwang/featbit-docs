import {Callout} from 'nextra/components'

# ライセンスキーのセットアップ

<Callout type="info">
  この記事はFeatBit 3.0.0以降と互換性があります。
</Callout>

このガイドは、ライセンスキーを使用してFeatBitを設定するプロセスを説明します。

## ワークスペースIDの取得

ライセンスキーを取得する前に、ワークスペースIDが必要です。以下の手順に従ってください：

1. FeatBitが実行中であることを確認し、FeatBit UIが http://localhost:8081 で利用可能であることを前提とします。
2. あなたのメールとパスワードを使用してFeatBitにログインします。デフォルト設定では、次を使用します：
   - ユーザーネーム: test@featbit.com
   - パスワード: 123456
  
3. http://localhost:8081/en/workspace に行き、**ライセンス設定**セクションで**コピー**ボタンをクリックします
   
   ![](./assets/workspaceid.png)

## 無料トライアルライセンスキーの取得

FeatBitのすべての機能を評価するために、[FeatBit Dashboard](https://dashboard.featbit.co/account)から無料のトライアルライセンスキーを生成します：

- メールを使ってアカウントを作成するか、GitHub経由でログインします。
- **アカウント**ページで**トライアルライセンスの生成**をクリックします。

  ![](./assets/request-trial-license1.png)
- モーダルにあなたの会社名とワークスペースIDを入力し、**OK**をクリックします。

  ![](./assets/request-trial-license2.png)
- ライセンステーブルで生成されたライセンスを見つけ、コピーをクリックします。

  ![](./assets/request-trial-license3.png)

## 商用ライセンスキーの取得

商用ライセンスキーについては、[contact@featbit.co](mailto:contact@featbit.co)にメールを送るか、私たちの[Slack Channel](https://join.slack.com/t/featbit/shared_invite/zt-1ew5e2vbb-x6Apan1xZOaYMnFzqZkGNQ)に加入し、迅速に対応します。
## ライセンスキーのアップロード

今度はhttp://localhost:8081/en/workspaceに戻り、**ライセンス設定**セクションに先ほど取得したライセンスキーを入力し、**更新**をクリックします。

![](./assets/save_license_key.png)

保存後、エンタープライズボタンにマウスを合わせると、次のようにライセンスの詳細を表示できます

![](./assets/check-license.png)