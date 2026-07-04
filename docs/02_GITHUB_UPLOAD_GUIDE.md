# 02 GitHubアップロード手順

## 前提

- リポジトリ名：`webrich-story-studio`
- 最初の公開：GitHub Pages
- 将来の本体URL：`https://story.webrich.info/`
- LPは別途：`https://webrich.info/story/`

## 1. GitHubで新規リポジトリを作る

1. GitHubにログインします。
2. 右上の「+」から「New repository」を選びます。
3. Repository name に `webrich-story-studio` と入力します。
4. Public / Private は、GitHub Pagesで無料公開するならPublicがわかりやすいです。
5. READMEは今回こちらで用意しているため、GitHub側で作らなくてもOKです。
6. 「Create repository」を押します。

## 2. ファイルをアップロードする

1. 作ったリポジトリを開きます。
2. 「Add file」→「Upload files」を押します。
3. 解凍したフォルダーの中身をアップロードします。
   - `index.html`
   - `README.md`
   - `docs` フォルダー
   - `manuals` フォルダー
   - `CNAME.example`
4. Commit message は以下でOKです。

```text
Initial WEBRICH Story Studio v1.4
```

5. 「Commit changes」を押します。

## 3. GitHub Pagesを有効化する

1. リポジトリの「Settings」を開きます。
2. 左メニューの「Pages」を開きます。
3. Sourceを「Deploy from a branch」にします。
4. Branchを `main`、Folderを `/root` にします。
5. Saveします。
6. 数分待つと公開URLが表示されます。

例：

```text
https://ユーザー名.github.io/webrich-story-studio/
```

## 4. 表示確認

公開URLを開き、次を確認します。

- ログイン画面が表示される
- オーナーデモで管理画面へ入れる
- 初回セットアップが動く
- 人生素材カードを登録できる
- note/Kindle/画像プロンプト画面が表示される
- スマホ幅でも崩れにくい

## 5. 注意

GitHub Pagesの設定画面や名称は変更される可能性があります。
画面の文言が多少違っても、基本は「Settings」→「Pages」→「Branch指定」です。

## 参考公式情報

- GitHub Pagesの公開元設定： https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- GitHub Pagesのカスタムドメイン： https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
