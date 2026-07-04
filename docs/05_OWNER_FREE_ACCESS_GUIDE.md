# 05 オーナー無料利用の実装方針

## 結論

オーナー無料利用は、別アプリに分けず、同じアプリ内で `role` と `plan` によって制御します。

```js
user: {
  role: "owner",
  plan: "owner-free",
  ownerFree: true
}
```

## なぜ同じアプリ内で管理するか

- UIや生成機能を二重管理しなくてよい
- オーナー自身が一般ユーザー画面も確認できる
- 将来、無料・有料・管理者の権限をまとめて管理できる
- Codexで修正するときに対象が分散しない

## 本番でやってはいけないこと

公開ログイン画面に、次のような選択肢は出しません。

- オーナー登録
- 無料で全機能を使う
- 管理者として登録

ユーザーが自分で選べる状態にすると、誰でも無料利用できてしまいます。

## 推奨する本番実装

### 方式A：オーナーメールのホワイトリスト

サーバー側、またはFirebase Functions / Cloudflare Workers側に、オーナーのメールアドレスを環境変数として保存します。

```text
OWNER_EMAILS=takebou2014@gmail.com
```

ログイン後、メールアドレスが一致した場合だけ、`role=owner` と `plan=owner-free` を付与します。

### 方式B：Firestoreのusersコレクションで管理

```text
users/{uid}
  displayName: "相棒"
  email: "takebou2014@gmail.com"
  role: "owner"
  plan: "owner-free"
  ownerFree: true
```

Firestoreのセキュリティルールで、本人のデータしか読めないようにします。

## 画面上の扱い

オーナーの場合だけ次を表示します。

- OWNER FREE
- オーナー無料アカウント
- 全機能確認可
- 料金制限なし

一般ユーザーには表示しません。
