# WEBRICH Story Studio v1.4 Complete Manual Package

WEBRICH Story Studio v1.4 は、AI物語作成サポートツールのGitHubアップロード準備版です。

中心コピー：

> 悩みを、宝物に変える。AIで、人生をもう一歩前へ。

## このパッケージに含まれるもの

- `index.html`：単体で動くツール本体（ローカル保存版）
- `CNAME.example`：サブドメイン `story.webrich.info` 用の参考ファイル
- `docs/`：GitHubアップロード、独自ドメイン、Codex、オーナー無料利用、次フェーズなどの手順書
- `manuals/`：総合手順書PDF・Markdown

## 現在の実装範囲

実装済み：

- シンプルなログイン／新規登録風画面
- オーナーデモ・一般ユーザーデモ
- 初回セットアップ
- レスポンシブ管理画面
- 人生素材カード
- 感情メモ
- 物語生成エンジン
- note記事生成のローカル下書き
- Kindle章立て生成のローカル下書き
- 画像プロンプト生成
- 記事管理
- 設定・規約ドラフト
- ローカル保存

未実装：

- Firebase Authによる本物のログイン
- Firestoreによるクラウド保存
- Cloudflare Workers / Firebase Functions経由のAI API接続
- 決済・料金プラン制御
- 正式な同意ログ保存
- 本番用の利用規約・プライバシーポリシー法務確認

## ②の位置づけ

このパッケージをGitHubへアップし、GitHub Pagesで表示確認できれば、
②「WEBRICH｜AI物語作成サポートツール」は、設計・UI・MVPスターター作成として一旦区切りです。

ただし、販売・本番運用としては未完成です。次フェーズで、認証・保存・AI API・決済を実装します。
