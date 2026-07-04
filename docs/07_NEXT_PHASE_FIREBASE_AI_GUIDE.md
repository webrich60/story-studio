# 07 次フェーズ：Firebase・AI API実装方針

## 次フェーズで入れるもの

- Firebase Auth
- Firestore保存
- ユーザー別データ管理
- オーナー無料権限
- AI API接続
- 利用規約同意ログ
- 料金プラン制御

## Firebase Auth

本番では、メールアドレス・パスワードとGoogleログインを使います。
Firebase Authenticationは、メール・パスワード認証やGoogleログインに対応しています。

## Firestore保存

保存する主なデータ：

```text
users/{uid}
materials/{materialId}
emotions/{emotionId}
articles/{articleId}
imagePrompts/{promptId}
settings/{uid}
consents/{consentId}
```

## AI API接続

APIキーはフロントエンドに置きません。

推奨構成：

```text
管理画面
↓
Cloudflare Workers / Firebase Functions
↓
Gemini API / OpenAI API
```

Cloudflare Workersでは、秘密情報はSecretsとして扱い、ダッシュボードやWrangler上で値が見えない形にできます。

## AI設定の考え方

ユーザーにはモデル名を細かく見せすぎず、次のようにします。

- 標準
- 低コスト
- 高品質

裏側でGemini / OpenAIを切り替えます。
本番実装時は、各社の公式モデル一覧に合わせてモデル名を更新してください。

## 要配慮情報

病歴・家族・借金・感情などの情報は、要配慮個人情報に当たり得ます。
入力は任意であること、公開範囲を選べること、AI生成文の確認責任がユーザーにあることを明示します。

## 参考公式情報

- Firebase Authentication： https://firebase.google.com/docs/auth
- Firebase Googleログイン： https://firebase.google.com/docs/auth/web/google-signin
- Cloudflare Workers 環境変数・Secrets： https://developers.cloudflare.com/workers/configuration/environment-variables/
- 個人情報保護委員会 要配慮個人情報FAQ： https://www.ppc.go.jp/all_faq_index/faq4-q011
