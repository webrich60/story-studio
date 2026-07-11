# オーナー無料利用・デモ制限設計

## デモ
- note記事生成：5回まで
- Kindle生成：1回まで
- 画像プロンプト：5回まで
- 保存：ブラウザ内localStorageのみ
- 目的：機能体験

## 無料登録
- Firebase Authでログイン
- Firestoreにクラウド保存
- 少量生成まで
- 有料プランへの導線を表示

## 有料プラン
- サブスク課金を想定
- 月間生成回数をプラン別に管理
- 使用回数はFirestoreで保存し、サーバー側でも制限する

## オーナー無料
- 公開ログイン画面には表示しない
- 通常ログイン後、Firebase側でメールアドレスやroleを見て判定
- role: owner
- plan: owner-free
- 制限なし

## 本番での重要事項
フロント側だけの制限は安全ではありません。
AI API接続後は Cloudflare Workers / Firebase Functions 側で role / plan / usage を確認し、制限超過時はAI生成を実行しない設計にしてください。
