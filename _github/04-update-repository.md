---
title: "リポジトリの更新"
permalink: /github/update-repository/
toc: true
---
「リポジトリの作成」では、「README.md」ファイルの作成をGitHub上で行いました。

GitHubでは、Webブラウザを通して、ファイルの作成・変更・削除が簡単にできるようになっています。

しかし、正常に機能していたプログラムが急に動かなくなるなどのリスクが高いため、基本的にはリモートリポジトリのファイルを直接操作することはしません。

通常は、ローカルリポジトリにて追加・変更を行い、十分に検証した後、リモートリポジトリを更新（push）します。

## ローカルリポジトリの更新

### README.mdファイルの更新

「リポジトリの作成」で作成したリポジトリを、ローカルで追加・変更します。

VSCodeを起動して、cloneしたリポジトリがあることを確認します。

<figure>
  <img src="{{ '/assets/images/github/04/vscode.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

「README.md」ファイルを表示させて、内容を変更します（自由に変更してください）。変更が終わったら、ファイルを保存します。

<figure>
  <img src="{{ '/assets/images/github/04/modify-readme.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

VSCodeはGitとの親和性が高い開発環境です。ファイルの状態が色の変化で分かるようになっています。
{: .notice--info} 

ターミナルのコマンドプロンプトの位置がリポジトリのフォルダになっているか確認します。もし違っていれば、以下のように「cd」コマンドで移動します。

```bash
cd test-repository
```

<figure>
  <img src="{{ '/assets/images/github/04/modify-readme2.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

ファイルの状態を確認します。以下のコマンドを実行します。

```bash
git status
```

<figure>
  <img src="{{ '/assets/images/github/04/modify-readme3.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

「Changes not staged for commit」と表示され、README.mdファイルが赤く表示されています。

これは、Gitに管理されていない変更が存在するということを示しています。変更をGitの管理に含めるには、以下のコマンドを実行します。

```bash
git add README.md
```

再度「git status」を実行して、状態を確認します。

<figure>
  <img src="{{ '/assets/images/github/04/modify-readme4.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

「Changes to be committed」と表示され、変更はGitの管理下となり、README.mdファイルが緑色に表示されました。

### hello.rbファイルの追加

今度は、hello.rbファイルを追加して、同様な操作をしてみましょう。

同じフォルダに「hello.rb」ファイルを新規作成して、中身を適当に書き、保存します。

<figure>
  <img src="{{ '/assets/images/github/04/hello-rb.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

同様に、「git status」で状態を確認、「git add hello.rb」でGit管理下にし、再度「git status」で状態を確認します。

<figure>
  <img src="{{ '/assets/images/github/04/hello-rb2.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

<figure>
  <img src="{{ '/assets/images/github/04/hello-rb3.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>


### 変更のコミット

Gitの管理下にあるファイルの変更（追加）を、履歴として残す（確定する）ことを、「コミットする」といいます。

「コミットする」には、以下のコマンドを実行します。

```bash
git commit -m "READMEの変更とhello.rbの追加" # クウォート内はコミットメッセージ
```

<figure>
  <img src="{{ '/assets/images/github/04/commit-error.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

（想定通り）エラーが発生しました。Gitの設定をしていませんでした。エラーの指示通りに、設定を行います。

以下のコマンドを実行します。

```bash
git config --global user.email "you@example.com" # 適宜書き換えてください
git config --global user.name "Your Name" # 適宜書き換えてください
```

再度、コミットコマンドを実行します。

コミット後、「git status」で状態を確認します。

<figure>
  <img src="{{ '/assets/images/github/04/re-commit.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

変更はコミットされて、クリーンな状態（管理下にない変更ファイル、管理下の変更ファイル、両方のない状態）になりました。

それでは、「git log」コマンドで、履歴を確認します。

<figure>
  <img src="{{ '/assets/images/github/04/git-log.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

先程コミットした履歴が追加されています。

## リモートリポジトリの更新

これまでの操作は、すべてローカルリポジトリで行ったもので、リモートリポジトリには全く影響はありません。

次に、ローカルで行った変更をリモートリポジトリに反映させます。

以下のコマンドを実行します。

```bash
git push origin main
```
「origin」はリモートリポジトリ（にデフォルトで付けられた名前）、「main」は対象のブランチ名を表しています。

<figure>
  <img src="{{ '/assets/images/github/04/push1.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

コマンドを実行すると、Githubへの認証を促すダイアログが表示されます。

ブラウザでの認証とPersonal Access Tokenによる認証の２種類が選択できます。ここでは、ブラウザ認証を選択します。

ここではブラウザ認証を行いましたが、セキュリティーや利便性から「Personal Access Token」の利用をお勧めします。
{: .notice--info} 

<figure>
  <img src="{{ '/assets/images/github/04/github-auth.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

すでにGitHubにログインしている状態であれば、すぐに以下の画面が表示されます。未ログインであればログイン画面が表示されますので、ログイン情報を入力すると、以下の画面が表示されます。

<figure>
  <img src="{{ '/assets/images/github/04/github-auth2.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

VSCodeのターミナルでは、認証されると、push処理が実行されます。

<figure>
  <img src="{{ '/assets/images/github/04/push2.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

ブラウザでGitHubのリポジトリを表示させると、変更が適用されていることが確認できます。

<figure>
  <img src="{{ '/assets/images/github/04/update-completed.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>
