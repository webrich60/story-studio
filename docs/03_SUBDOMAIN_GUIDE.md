# 03 サブドメイン接続手順

## おすすめ構成

```text
WEBRICH公式サイト： https://webrich.info/
商品LP：           https://webrich.info/story/
ツール本体：       https://story.webrich.info/
```

LPはフォルダー、本体はサブドメインに分けます。

## なぜサブドメインが良いか

- ツール本体を独立したサービスとして管理できる
- GitHubリポジトリを分けやすい
- Firebase AuthやAI API連携時にURL管理がしやすい
- AIスタッフツールや集客ツールと混ざりにくい

## GitHub側の設定

1. リポジトリのSettingsを開きます。
2. Pagesを開きます。
3. Custom domainに以下を入力します。

```text
story.webrich.info
```

4. Saveします。
5. HTTPSを有効化します。

## DNS側の設定

ドメイン管理会社側で、CNAMEレコードを追加します。

```text
種類：CNAME
名前：story
値：ユーザー名.github.io
```

GitHub Pages側のユーザー名に合わせてください。

## CNAMEファイル

GitHub PagesでCustom domainを保存すると、通常はCNAMEファイルが生成されます。
手動で用意する場合は、`CNAME.example` を `CNAME` にリネームして中身を以下にします。

```text
story.webrich.info
```

## 参考公式情報

- GitHub Pagesのカスタムドメイン設定： https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
- GitHub Pagesのカスタムドメイントラブル対応： https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/troubleshooting-custom-domains-and-github-pages
