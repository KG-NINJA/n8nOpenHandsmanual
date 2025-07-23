# n8nOpenHandsmanual

このリポジトリは、n8nの基本的な使い方や導入方法を日本語でまとめたものです。n8nを初めて使う方にも分かりやすい内容を目指しています。


## n8nとは？

n8nは、エンジニアや技術者向けのワークフロー自動化プラットフォームです。ノーコード/ローコードでさまざまなサービスやAPIを連携し、業務プロセスを自動化できます。

- オープンソースであり、自己ホストやクラウドで利用可能
- さまざまなサービス（Slack, Google, GitHubなど）と連携可能
- フローの作成・管理が直感的なUIで行える

## 基本的な使い方

1. n8nをインストールする
2. Web UIにアクセスし、ワークフローを作成
3. ノード（各種サービスや処理ステップ）をドラッグ＆ドロップで配置
4. ノード同士を接続し、データの流れを設計
5. ワークフローを保存し、実行

### インストール例（Docker）
```bash
# Dockerでn8nを起動
sudo docker run -it --rm \
  -p 5678:5678 \
  -e N8N_BASIC_AUTH_ACTIVE=true \
  -e N8N_BASIC_AUTH_USER=<ユーザー名> \
  -e N8N_BASIC_AUTH_PASSWORD=<パスワード> \
  n8nio/n8n
```

### サンプルワークフロー
例えば、Gmailで受信したメールをSlackに通知するワークフローを作成できます。

1. Gmailノードで新着メールを取得
2. Slackノードで通知を送信

## 参考リンク

## 主なノードの種類一覧

n8nには多くのノードが用意されており、以下のような種類があります（一部抜粋）：

### コアノード（基本機能）
- **Start**：ワークフローの開始点
- **Webhook**：外部からのHTTPリクエストでワークフローを開始
- **HTTP Request**：任意のAPIリクエストを送信
- **Function**：JavaScriptで独自の処理を記述
- **Set**：データの整形や値のセット
- **IF**：条件分岐
- **Switch**：複数条件で分岐
- **Merge**：複数のデータストリームを統合
- **Wait**：指定時間待機
- **Code**：TypeScript/JavaScriptで高度な処理
- **SplitInBatches**：データをバッチ処理
- **NoOp**：何もしないノード

### トリガーノード（ワークフローの起動）
- **Cron**：スケジュール実行
- **Email Trigger**：メール受信で起動
- **Webhook**：外部サービスからのリクエストで起動
- **IMAP Email**：IMAPメール受信で起動
- **Google Sheets Trigger**：Googleスプレッドシートの変更で起動

### サービス連携ノード（一部例）
- **Gmail**：メール送受信
- **Slack**：メッセージ送信・取得
- **Google Sheets**：スプレッドシートの読み書き
- **Trello**：カードやリストの操作
- **GitHub**：IssueやPRの管理
- **Dropbox**：ファイル操作
- **Twitter**：ツイートやDMの送信
- **Notion**：データベースやページの操作
- **Airtable**：データベース操作
- **Discord**：メッセージ送信
- **MySQL/PostgreSQL**：データベース操作
- **AWS S3**：ファイルのアップロード・ダウンロード

### その他
- **RSS Feed Read**：RSSフィードの取得
- **Pushbullet**：プッシュ通知
- **Twilio**：SMS送信
- **Microsoft Teams**：メッセージ送信

これら以外にも数百種類のノードがあり、さまざまなサービスやAPIと連携できます。

- [公式サイト](https://n8n.io/)
- [n8nドキュメント（英語）](https://docs.n8n.io/)
- [n8n GitHub](https://github.com/n8n-io/n8n)

