---
title: "GitHubのアカウント作成"
permalink: /github/create-github-account/
toc: true
---
## GitHubアカウントの作成

GitHubのウェブサイト（[https://github.com](https://github.com){:target="_blank"}）から、「Sign up」をクリックしてアカウントを作成してください。

<figure>
  <img src="{{ '/assets/images/github/02/github-website1.png' | relative_url }}" alt="GitHub" class="">
</figure>

E-mailアドレスを入力して、Continueボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/github/02/github-website2.png' | relative_url }}" alt="GitHub" class="">
</figure>

次に新しいパスワードを入力して、Continueボタンをクリックします。  
パスワードは15文字以上、または8文字以上で数字と半角小文字を含まなければなりません。

<figure>
  <img src="{{ '/assets/images/github/02/github-website3.png' | relative_url }}" alt="GitHub" class="">
</figure>

正しく入力できたら、下側に緑の線が表示されます。Continueボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/github/02/github-website4.png' | relative_url }}" alt="GitHub" class="">
</figure>

ユーザー名を入力します。世界中でユニーク（唯一）のものでなければなりません。Continueボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/github/02/github-website5.png' | relative_url }}" alt="GitHub" class="">
</figure>

メール案内を受け取るかどうかの設定です。不要であれば「n」を入力して、Continueボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/github/02/github-website6.png' | relative_url }}" alt="GitHub" class="">
</figure>

「アカウントの保護」の下の「検証する」ボタンをクリックします。（ロボットではなく）人間が操作をしている事を検証する画面が表示されます。

<figure>
  <img src="{{ '/assets/images/github/02/github-website7.png' | relative_url }}" alt="GitHub" class="">
</figure>

画面の指示に従って操作を行います。終わったら送信ボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/github/02/github-website8.png' | relative_url }}" alt="GitHub" class="">
</figure>

何回か同様の質問が表示される場合があります。問題なければ緑色のチェックマークが表示されます。「Create Account」ボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/github/02/github-website9.png' | relative_url }}" alt="GitHub" class="">
</figure>

登録したメールアドレスに、コードが記載されたメールが送信されます。そのコードを入力します。

<figure>
  <img src="{{ '/assets/images/github/02/github-website10.png' | relative_url }}" alt="GitHub" class="">
</figure>

正しく入力すると、「Welcome to GitHub」ページが表示されます。右側に、チームメンバーの数と、学生か先生かそれ以外かの質問が表示されますので、該当するラジオボタンをクリックして、Continueボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/github/02/github-website11.png' | relative_url }}" alt="GitHub" class="">
</figure>

右側に興味のある分野の一覧が表示されます。下までスクロールします。

<figure>
  <img src="{{ '/assets/images/github/02/github-website12.png' | relative_url }}" alt="GitHub" class="">
</figure>

Continueボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/github/02/github-website13.png' | relative_url }}" alt="GitHub" class="">
</figure>

プランが表示されます。下までスクロールします。

<figure>
  <img src="{{ '/assets/images/github/02/github-website14.png' | relative_url }}" alt="GitHub" class="">
</figure>

「Continue for Free」ボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/github/02/github-website15.png' | relative_url }}" alt="GitHub" class="">
</figure>

これでアカウントが作成されました。ダッシュボードが表示された状態になります。

<figure>
  <img src="{{ '/assets/images/github/02/github-website16.png' | relative_url }}" alt="GitHub" class="">
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
