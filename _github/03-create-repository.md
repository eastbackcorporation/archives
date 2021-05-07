---
title: "リポジトリの作成"
permalink: /github/create-repository/
toc: true
---
## リポジトリとは

リポジトリとは、ファイルなどを管理する場所の事です。通常、プロジェクトやサブプロジェクトごとにリポジトリを作成します。

リポジトリごとに、履歴を管理します。

リポジトリには、リモートリポジトリとローカルリポジトリがあります。リモートリポジトリは、サーバなどで管理し、中心的な役割を果たします。ローカルリポジトリは、PCなどで作業をするために作成します。

通常は、GitHubなどのサービスにリモートリポジトリを作成し、それをPCに複製してローカルリポジトリを作成します。ローカルリポジトリで作業を行った後、リモートリポジトリに変更を反映させます。

## リポジトリの作成方法

リポジトリを作成する方法は２種類あります。

1. GitHubに（リモート）リポジトリを作成して、ローカルにクローン（clone）する方法。

1. ローカルにリポジトリを作成し、GitHubにプッシュ（push）して、リモートリポジトリを作成する方法です。

通常、新規でリポジトリを利用する場合は、前者の方法を行います。既にローカルでgitを使ってリポジトリを管理している場合は、後者になります。

ここでは、GitHubにリポジトリを新規作成します。

## リモートリポジトリの作成

GitHubの「Sign in」ページを表示させます。ログイン情報を入力して「Sign in」ボタンを押してログインします。

<figure>
  <img src="{{ '/assets/images/github/03/login.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

Repositoriesの「New」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/03/create-repository.png' | relative_url }}" alt="Create Repository" class="img_border">
</figure>

リポジトリ作成画面が表示されます。「Repository name」にリポジトリ名を入力してください。

「Description」は、必須ではないですが、適当に入力します。「Public/Private」チェックボックスは、公開/非公開の設定です。ここでは公開設定とします。

チェックボックス３つありますが、ここでは全て空欄にします。

設定が終わったら、「Create Repository」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/03/repository-settings.png' | relative_url }}" alt="Repository Settings" class="img_border">
</figure>

空のリポジトリが作成されました。

<figure>
  <img src="{{ '/assets/images/github/03/repository-created.png' | relative_url }}" alt="Repository created" class="img_border">
</figure>

「…or create a new repository on the command line」や「…or push an existing repository from the command line」には、ローカルにある既存のフォルダやその中にある既存ファイルをリポジトリに含める手順が書かれています。
{: .notice--info} 

空の状態では面白くないので、GitHub上で、「README.md」ファイルを作成して登録してみます。

薄青四角部分に「Create a new file」リンクがありますので、クリックします。

<figure>
  <img src="{{ '/assets/images/github/03/create-readme.png' | relative_url }}" alt="Repository created" class="img_border">
</figure>

「Name your file...」フィールドに、「README.md」と入力します。

「Edit new file」の部分に、以下の様に入力します。

```bash
# テストリポジトリ
```

<figure>
  <img src="{{ '/assets/images/github/03/create-readme2.png' | relative_url }}" alt="Repository created" class="img_border">
</figure>

「md」拡張子のファイルは、Markdown記法で記述したファイルを表します。Markdownに関する情報は検索すると数多く出てくるので、好きな内容を追記してください。
{: .notice--info} 

「Preview」タブをクリックすると、（Markdown記法の）見た目を確認できます。

<figure>
  <img src="{{ '/assets/images/github/03/create-readme3.png' | relative_url }}" alt="Repository created" class="img_border">
</figure>

「README.md」ファイルを登録（commit）します。

「Commit new file」の最初のフィールドは、コミットメッセージを書くところです。「Create README.md」と薄く表示されています。このままでもよいですし、自分で分かりやすいコミットメッセージを上書きしても結構です。下のフィールドは、詳細なメッセージを書く欄です。

「Commit new file」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/03/create-readme4.png' | relative_url }}" alt="Repository created" class="img_border">
</figure>

リポジトリに「README.md」フィアルが登録されました。

GitHubでは、「README」ファイルが存在すると、中身を表示してくれます。通常、「README」ファイルには、リポジトリ（プログラム）の説明や、使い方の説明などを記入します。

## ローカルリポジトリの作成

次に、ローカルリポジトリを作成します。新規に作成するのではなく、先程作成したGitHub上のリモートリポジトリの複製（クローン）を作成します。

コマンドプロンプトを起動してもよいですが、ここではVisual Studio Code（以下VSCode）のターミナル（コマンドプロンプト）から実行します。

VSCodeを起動します。もし、ターミナルが表示されていなければ、メニューから「ターミナル」=>「新しいターミナル」をクリックして表示させます。

ターミナルのコマンドプロンプトのパスが「C:\ruby_lecture\code」であることを確認してください。

<figure>
  <img src="{{ '/assets/images/github/03/vscode.png' | relative_url }}" alt="Repository created" class="img_border">
</figure>

一応、Gitコマンドが使えることを確認します。

ターミナルに以下のコマンドを入力して実行します。

```bash
git --version
```

Gitのバージョンが表示されればOKです。

<figure>
  <img src="{{ '/assets/images/github/03/vscode2.png' | relative_url }}" alt="Repository created" class="img_border">
</figure>

ブラウザで、先程作成したGitHubのリポジトリを表示させます。「Code」ボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/github/03/repository-code.png' | relative_url }}" alt="Repository created" class="img_border">
</figure>

ダイアログが表示されます。このリポジトリのURLが表示されているフィールドの右側にあるアイコンをクリックします。クリップボードにURLがコピーされます。

<figure>
  <img src="{{ '/assets/images/github/03/repository-code2.png' | relative_url }}" alt="Repository created" class="img_border">
</figure>

VSCodeのターミナルに以下のコマンドを入力します。

```bash
git clone # 最後に半角スペースを入れる
```

続けて「Ctrl-v」（コントロールキーを押しながらvキーを押す）で、コピーしたURLをペーストします。

<figure>
  <img src="{{ '/assets/images/github/03/git-clone.png' | relative_url }}" alt="Repository created" class="img_border">
</figure>

エンターキーを押します。リポジトリがダウンロードされます。左側のツリーにリポジトリ名のフォルダが表示されています。

<figure>
  <img src="{{ '/assets/images/github/03/git-clone2.png' | relative_url }}" alt="Repository created" class="img_border">
</figure>

ツリーのフォルダを展開すると、README.mdファイルがあります。ダブルクリックして開き、中身を確認します。

<figure>
  <img src="{{ '/assets/images/github/03/git-clone3.png' | relative_url }}" alt="Repository created" class="img_border">
</figure>

ローカルリポジトリは、単なるファイルをダウンロードしたものではありません。リモートリポジトリのGitが管理している履歴も含まれています。

VSCodeのターミナルで、以下のコマンドを実行します。

```bash
cd test-repository
git log
```

リモートリポジトリで行った「Create README.md」のコミットメッセージが表示されます。

<figure>
  <img src="{{ '/assets/images/github/03/git-log.png' | relative_url }}" alt="Repository created" class="img_border">
</figure>
