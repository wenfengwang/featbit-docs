# Relay Proxy

## 概要 

このトピックでは、FeatBit Relay Proxyの設定を作成し、FeatBit Agentに接続する方法について説明します。FeatBit Agentが何であるかわからない場合は、この[ドキュメント](featbit-agent.md)をお読みください。

## エージェントのステータス

FeatBit UIでは、以下のエージェントのステータスが表示されます：

* Healthy：エージェントは健全な状態で、すべてが正常に機能しています
* Unhealthy：エージェントに何らかの問題があります
* Unreachable：エージェントが利用できません。通常は、エージェントが起動されていないか、エージェントホストのURLが正しくないためです
* Unauthorized：このステータスが表示された場合、FeatBit Agentを起動する際に使用したApiKeyがリレープロキシキーと一致していないことを意味します

## リレープロキシの作成と管理を制限する 

リレープロキシの設定を作成するには、**ManageRelayProxies** と **ListRelayProxies** の権限が必要です。組み込みポリシー（Owner、Administrator、Developer）のいずれかを持っている場合、これらの権限は既に付与されています。

![](../relay-proxy/assets/relay-proxy/001.webp)

## リレープロキシの設定を作成する

リレープロキシの設定は、**Relay Proxies**ページから作成できます。

1. **Relay Proxies**ページに移動します。

![](../relay-proxy/assets/relay-proxy/002.png)
2. ページの右上にある**Add**ボタンをクリックすると、**Add Relay Proxy**パネルが表示されます\
![](../relay-proxy/assets/relay-proxy/003.png)
3. トークンにわかりやすい**Name**と説明**Description**を設定します。
4. スコープを設定：エージェントにフィーチャーフラグとセグメントを同期したい環境を選択します。
5. エージェント名とホストを設定します
6. **Save**ボタンをクリックします。
7. キーをコピーして安全な場所に保存してください。このページを離れると、キーは見えなくなります。

![](../relay-proxy/assets/relay-proxy/004.png)

リレープロキシを作成した後、編集や削除が可能です。このページから既存のリレープロキシも管理できます。

## フィーチャーフラグとセグメントをエージェントに同期する

現在、手動での同期のみをサポートしています。これを行うには、リレープロキシの**Edit**ボタンをクリックし、編集パネルの**Sync**ボタンをクリックします。すると、選択したスコープのフィーチャーフラグとセグメントがエージェントに同期されます。

![](../relay-proxy/assets/relay-proxy/005.png)

## FeatBit Agentのステータスをチェックする

エージェントには異なるステータスがあります。それを更新するか、何か問題がある場合にデバッグするには、ステータスラベルをクリックします。すると、エージェントの詳細なステータスが表示されるモーダルが開きます。**lastSyncAt**の値はUTCタイムゾーンです。

![](../relay-proxy/assets/relay-proxy/006.png)

## リレープロキシを管理する

リレープロキシを管理するには：

1. **Relay Proxies**ページに移動します。
2. リストからプロキシを見つけます。
3. **edit**ボタンまたは**remove**ボタンをクリックします

リレープロキシのステータスをチェックできます：

* すべてのエージェントがHealthy状態の場合、色は**green**です
* 少なくとも1つのエージェントがHealthyでない場合、色は**red**です

![](../relay-proxy/assets/relay-proxy/007.png)

## FeatBit AgentをFeatBit UIに接続する

リレープロキシの設定を作成した後、キーを安全な場所に保存しておきます。そのキーをApiKeyパラメータの値として使用し、FeatBit Agentを起動してください。詳細は[FeatBit Agentのインストール](https://github.com/featbit/featbit-agent#installation)をご覧ください。
