---
title: "ブランチの操作"
permalink: /github/use-branch/
toc: true
---
## ブランチとは

ブランチとは、日本語で「木の枝」という意味です。

リポジトリ本体を変更していくと、誤って動かないプログラムやバグのあるプログラムをcommitしてしまい、不具合のあるプログラム（アプリ）を世の中に発信してしまう可能性があります。

通常、「main」ブランチは、必ず（問題なく）動くプログラムを置く場所として確保しておき、開発は「main」ブランチを派生させた別のブランチで行います。

木に例えると、「main」ブランチが木の幹で、幹から枝（別のブランチ）を作るようなイメージです（枝から枝を作ることもできます。）。

開発用ブランチで十分にバグフィックスを行い、テストを行った上で、問題ないと判断したら「main」ブランチに統合（merge）します。

## ブランチのコマンド

### ブランチの一覧

以下のコマンドで、ブランチの一覧を表示します。

```bash
git branch
```

現時点では、「main」ブランチしかありません。

<figure>
  <img src="{{ '/assets/images/github/05/branch1.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>


### ブランチの作成

以下のコマンドで、ブランチを作成します。

```bash
git branch ブランチ名
```

ここでは、「test1」というブランチを作成してみます。

このコマンドを実行すると、現在使用している「main」ブランチとファイルを持つ「test1」ブランチが作成されます。

※ 空のブランチが作成される訳ではありません。

ブランチの一覧を表示します。「*」（アスタリスク）の付いているブランチが、現在使用しているブランチです。

<figure>
  <img src="{{ '/assets/images/github/05/branch2.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

### ブランチの切り替え

以下のコマンドで、ブランチを切り替えます。

```bash
git checkout ブランチ名
```

「test1」ブランチに切り替えて、一覧を表示させると「*」の位置が変更されています。

<figure>
  <img src="{{ '/assets/images/github/05/branch3.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

## リモートリポジトリへの更新

先程作成した「test1」ブランチは、このPCのローカルリポジトリでのみ存在します。

それでは、「test1」ブランチで変更を行って、リモートリポジトリにアップロード（push）します。

### 「test1」ブランチでの変更

「リポジトリの変更」の要領で、hello.rbファイルの変更とhello2.rbファイルを新規作成します。

※ 自由に書き換えてください。

<figure>
  <img src="{{ '/assets/images/github/05/branch4.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

<figure>
  <img src="{{ '/assets/images/github/05/branch5.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

変更を一括してGit管理下（ステージングといいます）にするには、以下のコマンドを実行します。

```bash
git add .
```

<figure>
  <img src="{{ '/assets/images/github/05/branch6.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

<figure>
  <img src="{{ '/assets/images/github/05/branch7.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

コミットします。

※ コミットメッセージは何でも結構です。

<figure>
  <img src="{{ '/assets/images/github/05/branch8.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

### リモートリポジトリへのpush

ここでは、「test1」ブランチをpushしますので、以下のコマンドを実行します。

```bash
git push origin test1
```

<figure>
  <img src="{{ '/assets/images/github/05/branch9.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

GitHubのリポジトリの画面を開きます（更新します）。「branches」の数が1から2に増えています。

<figure>
  <img src="{{ '/assets/images/github/05/branch10.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

「main」ボタンを押すと、ブランチを選択できます。「test1」ブランチを表示させて、内容を確認します。

<figure>
  <img src="{{ '/assets/images/github/05/branch11.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

<figure>
  <img src="{{ '/assets/images/github/05/branch12.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>
