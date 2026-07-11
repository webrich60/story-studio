# WEBRICH Story Studio v1.5 Owner First

WEBRICH Story Studio は、人生経験を note 連載・Kindle 原稿・画像プロンプトへ整理するための AI 物語作成サポートツールです。

## v1.5 の主な変更点

- ログイン画面から「オーナーデモ」を削除
- デモ利用は「デモではじめる」に統一
- 利用規約・プライバシーポリシーをモーダル表示
- 最後までスクロール後に「内容を確認しました」ボタンが有効化
- 同意チェックが揃うまでログイン / 新規登録ボタンを無効化
- デモ利用の生成制限を追加
  - note記事生成：5回まで
  - Kindle生成：1回まで
  - 画像プロンプト：5回まで
- 設定画面に使用回数とプラン表示を追加
- オーナー無料利用は画面に出さず、Firebase連携後に裏側で role=owner / plan=owner-free として付与する設計に整理

## 現在の位置づけ

この v1.5 は、GitHub Pages 上で動作確認できるローカル保存版です。
本番では Firebase Auth / Firestore / Cloudflare Workers または Firebase Functions を接続します。

## 次フェーズ

1. GitHub Pagesで表示確認
2. Firebase Authを実装
3. Firestore保存を実装
4. owner-free 権限をFirebase側で付与
5. Gemini / OpenAI API接続
6. Stripe等でサブスク決済を検討

## 注意

APIキーや秘密鍵はGitHubに入れないでください。
AI APIキーは Cloudflare Workers Secret や Firebase Functions Secret 等で管理する想定です。
