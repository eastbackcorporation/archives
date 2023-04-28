---
title: "GitHubのアカウント作成"
permalink: /github/create-github-account/
toc: true
---
## GitHubアカウントの作成

GitHubのウェブサイトから、「Sign up」をクリックしてアカウントを作成してください。

<figure>
  <img src="{{ '/assets/images/github/02/github-website.png' | relative_url }}" alt="GitHub" class="img_border">
</figure>

## Gitのインストール

Macには、デフォルトでGitがインストールされています。

ここでは、Windows10にGitをインストールする手順を示します。

ブラウザから、「[Git for Windows](https://gitforwindows.org/){:target="_blank"}」を検索して、Webサイトを表示させます。

Webサイトの「Download」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/02/git-for-windows.png' | relative_url }}" alt="Git for Windows" class="img_border">
</figure>

インストーラーがダウンロードされます。

インストーラーを起動させ、「Next」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/02/git-installer1.png' | relative_url }}" alt="Git for Windows" class="img_border">
</figure>

インストール先が問題なければ、「Next」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/02/git-installer2.png' | relative_url }}" alt="Git for Windows" class="img_border">
</figure>

インストールするコンポーネントが表示されます。そのまま「Next」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/02/git-installer3.png' | relative_url }}" alt="Git for Windows" class="img_border">
</figure>

スタートメニューフォルダの設定が表示されます。そのまま「Next」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/02/git-installer4.png' | relative_url }}" alt="Git for Windows" class="img_border">
</figure>

テキストエディタの設定が表示されます。デフォルトでは「Vim」を使うようになっています。そのまま「Next」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/02/git-installer5.png' | relative_url }}" alt="Git for Windows" class="img_border">
</figure>

リポジトリを新規作成した時のブランチ名（「マージとプルリクエスト」で説明します）の設定が表示されます。

これまで、Gitのデフォルトブランチ名は「master」でした。しかし、近年「master」は差別用語になるとの意見があり、GitHubをはじめ、その他リポジトリサービスでは、「main」をデフォルトブランチ名にする動きがあります。今回は、GitHubを使いますので、「main」の方のラジオボタンを選択します。「Next」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/02/git-installer6.png' | relative_url }}" alt="Git for Windows" class="img_border">
</figure>

Gitを何から使うかの設定が表示されます。ここではコマンドプロンプトから実行させますので、デフォルトのままにします。「Next」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/02/git-installer7.png' | relative_url }}" alt="Git for Windows" class="img_border">
</figure>

HTTPSで通信するライブラリの設定が表示されます。デフォルトのOpenSSLままにします。「Next」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/02/git-installer8.png' | relative_url }}" alt="Git for Windows" class="img_border">
</figure>

改行コード（LFやCRLF）の処理の設定が表示されます。そのまま「Next」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/02/git-installer9.png' | relative_url }}" alt="Git for Windows" class="img_border">
</figure>

Git Bash使用時のターミナルの設定が表示されます。Git Bashは使いませんので、そのまま「Next」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/02/git-installer10.png' | relative_url }}" alt="Git for Windows" class="img_border">
</figure>

git pullコマンド実行時の設定が表示されます。そのまま「Next」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/02/git-installer11.png' | relative_url }}" alt="Git for Windows" class="img_border">
</figure>

Git Credential Manager（Gitにアクセスする時表示されるユーザー、パスワード入力ダイアログ）の使用の設定が表示されます。そのまま「Next」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/02/git-installer12.png' | relative_url }}" alt="Git for Windows" class="img_border">
</figure>

オプションの設定が表示されます。そのまま「Next」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/02/git-installer13.png' | relative_url }}" alt="Git for Windows" class="img_border">
</figure>

実験的なオプションの設定が表示されます。そのまま「Install」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/02/git-installer14.png' | relative_url }}" alt="Git for Windows" class="img_border">
</figure>

インストールが開始されます。しばらく待つと、インストールが終了します。

リリースノートの表示が必要なければ、チェックを外して、「Finish」ボタンを押します。インストーラーが閉じます。

<figure>
  <img src="{{ '/assets/images/github/02/git-installer15.png' | relative_url }}" alt="Git for Windows" class="img_border">
</figure>

Gitがインストールされているか確認します。

コマンドプロンプトを起動して、以下のコマンドを実行します。

```bash
git --version
```

Gitのバージョンが表示されれば、問題なくインストールされています。

<figure>
  <img src="{{ '/assets/images/github/02/git-install-check.png' | relative_url }}" alt="Git for Windows" class="img_border">
</figure>
