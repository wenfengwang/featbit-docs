import {Callout} from 'nextra/components'

# ライセンスキーの設定

<Callout type="info">
  この記事は FeatBit 3.0.0 以降と互換性があります。
</Callout>

このガイドでは、ライセンスキーを使用して FeatBit の設定方法を示します。

## ワークスペース ID の取得

ライセンスキーを取得する前に、ワークスペース ID が必要です。次の手順に従ってください。

1. FeatBit が実行されていることを確認し、FeatBit ユーザーインターフェースが http://localhost:8081 で利用可能であると想定します。
2. メールアドレスとパスワードを使用して FeatBit にログインします。デフォルトの設定の場合、次の情報を使用します：
   - ユーザー名：test@featbit.com
   - パスワード：123456
   
3. http://localhost:8081/en/workspace に移動し、**ライセンス設定** セクションで **コピー** ボタンをクリックします。
   
   ![](./assets/workspaceid.png)

## 無料トライアルライセンスキーの取得

すべての FeatBit の機能を評価するために、[FeatBit ダッシュボード](https://dashboard.featbit.co/account)から無料トライアルライセンスキーを生成します：

- メールアドレスを使用してアカウントを作成するか、GitHub を介してログインします。
- **アカウント** ページで **トライアルライセンスを生成** をクリックします。

  ![](./assets/request-trial-license1.png)
- モーダルに会社名とワークスペース ID を入力し、**OK** をクリックします。

  ![](./assets/request-trial-license2.png)
- ライセンステーブル内の生成されたライセンスを見つけ、コピーをクリックします。

  ![](./assets/request-trial-license3.png)

## 商用ライセンスキーの取得

商用ライセンスキーを取得するには、[contact@featbit.co](mailto:contact@featbit.co) までメールを送信するか、[Slack チャンネル](https://join.slack.com/t/featbit/shared_invite/zt-1ew5e2vbb-x6Apan1xZOaYMnFzqZkGNQ)に参加し、迅速に対応します。
## ライセンスキーのアップロード

次に、http://localhost:8081/en/workspace に戻り、**ライセンス設定** セクションに移動し、以前に取得したライセンスキーを入力し、**更新** をクリックします。

![](./assets/save_license_key.png)

保存したら、エンタープライズボタンの上にカーソルを合わせると、以下のようにライセンスの詳細を表示することができます。

![](./assets/check-license.png)