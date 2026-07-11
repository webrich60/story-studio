# Firebase連携 次の実装手順

## 1. Firebase Auth
- メール/パスワード認証
- Googleログイン
- 同意済みフラグの保存
- 規約更新時の再同意

## 2. Firestore構成案

users/{uid}
- displayName
- email
- role: user / owner / admin
- plan: demo / free / paid / owner-free
- consentVersion
- usage

users/{uid}/lifeCards/{cardId}
users/{uid}/emotionMemos/{memoId}
users/{uid}/articles/{articleId}
users/{uid}/imagePrompts/{promptId}

## 3. オーナー判定
- 自分のログインメールを管理者側で ownerEmails に登録
- ログイン後に role=owner / plan=owner-free を付与
- 公開画面にはオーナー登録ボタンを出さない

## 4. AI API接続
- APIキーはフロントに置かない
- Cloudflare Workers Secret または Firebase Functions Secret で管理
- 生成前に usage と plan を検証
