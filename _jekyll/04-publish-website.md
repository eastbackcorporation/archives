---
title: "ウェブサイトの公開"
permalink: /jekyll/publish-website/
toc: true
---
## サイトの公開方法
[[ウェブサイトの作成]-[_site]](../create-website/#_site)でも書いたように、基本的には、**_site**フォルダの中身すべてをウェブサーバーに置くことで、ウェブサイトを公開することができます。

ウェブサーバーを提供するサービスに登録したり、プロバイダーと契約することで利用することができますが、多くの場合は、利用料金が発生します。  
ここでは、無料で利用できるGitHub Pagesを使ったウェブサイトの公開方法を説明します。

※ GitHub Pagesが指定するRubyおよびJekyllのバージョンを使用する必要があります。[^1]  

[^1]: GitHub Pagesで利用できるバージョン一覧（Dependency versions）: [https://pages.github.com/versions/](https://pages.github.com/versions/){:target="_blank"}

## GitHub Pagesとは
**GitHub Pages**とは、GitHubが提供している静的ウェブサイトホスティングサービスです。GitHubのリポジトリを使って、無料のウェブサイトを公開することができます。

[GitHub Pagesについて](https://docs.github.com/ja/pages/getting-started-with-github-pages/about-github-pages){:target="_blank"}

※ ただし、利用上の制限に従う必要があります。[^2]

[^2]: [GitHub Pagesの利用上の制限](https://docs.github.com/ja/pages/getting-started-with-github-pages/about-github-pages#github-pagesの利用上の制限){:target="_blank"}

GitHub Pagesで使用するリポジトリ名およびサイトURLは、ルールによって決められていますが、独自ドメインを設定することもできます。[^3]

[^3]: [カスタムドメインとGitHub Pagesについて](https://docs.github.com/ja/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages){:target="_blank"}

## リポジトリの作成
最初に、GitHub Pages用のリポジトリを作成します。  
リポジトリ名は、`<user>.github.io`（`<user>`はGitHubユーザー名）に設定します。公開（public）に設定して、リポジトリを作成します。

[サイト用にリポジトリを作成する](https://docs.github.com/ja/pages/getting-started-with-github-pages/creating-a-github-pages-site#creating-a-repository-for-your-site){:target="_blank"}

## ローカルリポジトリの作成
ブラウザで作成したGitHubリポジトリのページを表示します。

Visual Studio Code（以下、VSCode）を起動し、アプリを置く適当なフォルダ（ここでは**C:/jekyll_lecture/**）を開きます。  
ターミナルを開きます。

ブラウザ画面に表示されている「< > Code」ボタンを押して、表示されるURLをコピーします。以下のコマンドを実行します（clone以下に、コピーしたURLを貼り付けます）。

```bash
git clone https://github.com/<user>/<user>.github.io.git
```

`<user>.github.io.git`フォルダが作成されます。  

### Jekyllのデフォルトテーマ(minima)を使用する場合
以下のコマンドを実行します。

```bash
jekyll new  --skip-bundle <user>.github.io.git
```

`<user>.github.io.git`フォルダの中に**Jekyllサイト**が作成されます。

以下の「サイトを作成する」の&#10108;から&#10111;まで行います。

[サイトを作成する](https://docs.github.com/ja/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll#creating-your-site){:target="_blank"}


### 「Bulma Clean Theme」を使用する場合
[Bulma Clean Theme](https://www.csrhymes.com/bulma-clean-theme/){:target="_blank"}を使用します。[^4]

[^4]: Bulma Clean Theme GitHubリポジトリ: [https://github.com/chrisrhymes/bulma-clean-theme](https://github.com/chrisrhymes/bulma-clean-theme){:target="_blank"}

最小構成から始める方法もありますが、ここでは、「Bulma Clean Theme」サイトのデータをそのまま利用し、それをカスタマイズしていきます。  
以下のURLからZIPファイルをダウンロードします。

[https://download.eastback.co.jp/jekyll/bulma-clean-theme.zip](https://download.eastback.co.jp/jekyll/bulma-clean-theme.zip)

展開した後、中のすべてのファイルを`<user>.github.io.git`フォルダにコピーまたは移動します。

※ Macの場合、Gemfileの最後の部分の「for Windows」と「for Mac」のコメントを入れ替えてください。

## 動作確認

次に、以下のコマンドを実行します。

```bash
cd <user>.github.io.git
bundle install
bundle exec jekyll serve
```

※ `bundle`や`bundle exec`は、**bundler**（Rubyパッケージ管理ツール）を使うためです。  
※　**eventmachine**に関するエラーが発生する場合があります。[^5]

[^5]: eventmachineエラー対処法: [https://mebee.info/2020/07/21/post-14764/](https://mebee.info/2020/07/21/post-14764/){:target="_blank"}

ウェブサーバーが起動したら、以下のURLをブラウザで表示させます。

[http://localhost:4000](http://localhost:4000){:target="_blank"}

サイトが表示されます。  
ウェブサイトの確認が終わったら、VSCodeのターミナルで**Ctrl + c**（コントロールキーを押しながらCキーを押す）を押して、ウェブサーバーを終了させます。

## リモートリポジトリの更新
ローカルリポジトリの内容（変更）をリモート（GitHub）リポジトリに反映させます。  
以下のコマンドを実行します。

```bash
git add .
git commit -m "First Commit"
git push origin main
```

※ コミットメッセージは何でも結構です。  
※ コミット時に「git config」に関するエラーが表示された場合は、エラー内容に従って設定してください。  
※ プッシュ時に認証エラーが表示された場合は、適切に認証設定をしてください。  

ブラウザのGitHubリポジトリのページを表示させて、ローカルの内容が反映されたかどうか確認します。

# GitHub Pagesの設定
ブラウザのGitHubリポジトリのページの「Settings」をクリックします。  
左側のサイドメニューから「Pages」をクリックします。  
以下の「ブランチからの公開」の&#10106;から&#10108;まで行います。

[ブランチからの公開](https://docs.github.com/ja/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-from-a-branch){:target="_blank"}

以下の「サイトを作成する」の&#9459;を行います。

[サイトを作成する](https://docs.github.com/ja/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll#creating-your-site){:target="_blank"}

ウェブサイトが公開されていることを確認します。
