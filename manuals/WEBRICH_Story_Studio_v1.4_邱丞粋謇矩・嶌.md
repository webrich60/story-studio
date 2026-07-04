# WEBRICH Story Studio v1.4 総合手順書

## 1. ツールの目的

WEBRICH Story Studioは、人生経験をnote連載・Kindle原稿・画像プロンプトへ変えるAI物語作成サポートツールです。

中心コピー：

> 悩みを、宝物に変える。AIで、人生をもう一歩前へ。

## 2. 現在の状態

v1.4は、GitHubへアップロードできるローカル保存版スターターです。

実装済み：

- ログイン／新規登録風画面
- オーナーデモ
- 初回セットアップ
- 管理画面UI
- 人生素材カード
- 感情メモ
- 物語生成エンジン
- note記事生成下書き
- Kindle章立て下書き
- 画像プロンプト生成
- 記事管理
- 設定・規約ドラフト

未実装：

- Firebase Auth
- Firestore保存
- AI API接続
- 決済
- 同意ログ保存
- 本番規約の法務確認

## 3. ローカル確認手順

1. ZIPを解凍します。
2. `index.html` をChromeで開きます。
3. 「オーナーデモで確認」を押します。
4. 初回セットアップを進めます。
5. 管理画面に入り、人生素材カードなどを確認します。

## 4. GitHubアップロード手順

1. GitHubで `webrich-story-studio` というリポジトリを作ります。
2. 解凍したフォルダーの中身をアップロードします。
3. GitHub Pagesを有効化します。
4. Branchを `main`、Folderを `/root` にします。
5. 公開URLで表示を確認します。

## 5. サブドメイン構成

おすすめ構成：

```text
WEBRICH公式サイト： https://webrich.info/
商品LP：           https://webrich.info/story/
ツール本体：       https://story.webrich.info/
```

ツール本体はサブドメインで管理すると、AIスタッフツールや集客ツールと分けやすくなります。

## 6. オーナー無料利用

本番では、公開ログイン画面に「オーナー登録」は出しません。
Firebase Authでログインしたメールを見て、サーバー側で `role=owner` と `plan=owner-free` を付与します。

例：

```text
takebou2014@gmail.com
→ role: owner
→ plan: owner-free
```

## 7. Codexへの最初の指示

GitHubにアップしたら、Codexには最初に以下を貼ります。

```text
このリポジトリは WEBRICH Story Studio v1.4 です。
まず全体構成を調査してください。
まだコードは変更しないでください。
現在の構成、UI、保存方式、未実装機能、次に実装すべき順番を日本語で整理してください。
```

## 8. 次フェーズで実装するもの

- Firebase Auth
- Firestore保存
- Cloudflare Workers / Firebase Functions経由のAI API接続
- オーナー無料権限
- 料金プラン
- 利用規約同意ログ
- 特商法表記

## 9. ②の完了判定

v1.4をGitHubにアップし、GitHub Pagesで表示確認できた時点で、②は一旦完了です。

ただし、これは「設計・UI・スターター作成」の完了です。
販売できる完成品ではありません。

## 10. 次に進むなら

おすすめは、次の流れです。

1. GitHubへアップ
2. GitHub Pagesで表示確認
3. Codexに調査だけ依頼
4. Firebase Auth実装
5. Firestore保存実装
6. AI API接続
7. LP・料金・規約の正式化

