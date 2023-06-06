---
title: "ウェブサイトのカスタマイズ"
permalink: /jekyll/customize-website/
toc: true
---
## ウェブサイトのカスタマイズ
[ウェブサイトの公開](../publish-website/)では、デフォルトテーマ（minima）の**Jekyllサイト**、またはBulma Clean Themeの**Jekyllサイト**をそのままリポジトリに置くことで、GitHubが自動的にbuildを実行し、GitHub Pagesのサイトが表示されることを確認しました。

ここでは、**Jekyllサイト**をカスタマイズして、独自のウェブサイトに更新していきます。

### _config.yml
**_config.yml**は、Jekyllの設定ファイルです。ウェブサイトのヘッダーなど、基本的なHTMLの設定などをします。

※ _config.ymlファイルは、テーマによって設定項目が変わります。詳しくは、使用するテーマのREADMEファイルやマニュアルを確認してください。

### _layouts
ウェブサイトで、複数のタイプのレイアウトを扱う場合、あらかじめ**_layouts**フォルダに複数のレイアウトファイルを作成します。

### _includes
ウェブサイトのデザインをいくつかのコンポーネントに分割し、共通化して使い回すためにファイルを置きます。デザインのメンテナンス性が向上します。

## `<user>.github.io`以外のリポジトリをGitHub Pagesとして公開する
その他のリポジトリをGitHub Pagesとして公開することもできます。  
その場合のURLは、`<user>.github.io/<リポジトリ名>`となります。

※ **プロジェクトサイト**と呼びます。

[GitHub Pages サイトの種類](https://docs.github.com/ja/pages/getting-started-with-github-pages/about-github-pages#github-pages-サイトの種類){:target="_blank"}

## 独自ドメインの設定
GitHub PagesのURLは、`<user>.github.io`または`<organization>.github.io`ですが、独自（カスタム）ドメインを設定することができます。

[GitHub Pages サイトのカスタムドメインを管理する](https://docs.github.com/ja/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site){:target="_blank"}

※ プロジェクトサイトも独自ドメインを設定することができます。
