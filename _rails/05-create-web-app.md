---
title: "ウェブアプリの雛形作成"
permalink: /rails/create-web-app/
toc: true
---
## scaffoldについて
**scaffold**とは、Railsの機能の一つで、ウェブアプリの雛形を簡単に作ることができます。

この雛形は、以下の機能を持ちます。

- **scaffold**実行時に、ウェブアプリに必要な**データ（と型）**を指定できます。
- 自動的に、データを保存する**データベース**を作成します。
- 作成したウェブアプリは、データの**登録、編集、削除、一覧表示、個別表示**の機能を持ちます。

## ブログアプリの作成

ここでは、**scaffold**を使って**ブログアプリ**を作っていきます。

### ブログアプリの設計

一般的なブログアプリは、どんなデータを持っているでしょうか。

- ユーザ（投稿者）のアカウント
- ユーザのプロフィール
- ブログ記事

ブログ記事には、どんなデータが必要でしょうか。

- 投稿者名
- 投稿日
- タイトル
- 内容
- 画像
- カテゴリ

ここでは、アプリを簡単にするために、**ブログ記事**の部分のみ作ります。

### scaffoldの設定

**scaffold**は、以下のようなコマンドで実行します。

```bash
rails generate scaffold モデル名 データ名1:データ型1 データ名2:データ型2 ・・・ データ名n:データ型n
```

**モデル名**とは、**scaffold**で作る機能（アプリ）の名前です。
{: .notice--info}

ここでは、ブログ記事を作成するので、モデル名は**blog**とします。

データ型は、以下の種類があります。

- string: 文字列
- text: テキスト（長い文字列）
- integer: 整数
- float: 実数（浮動小数）
- decimal: 制度の高い実数
- boolean: 真偽値
- binary: バイナリ
- date: 日付
- time: 時間
- datetime: 日時
- timestamp: タイムスタンプ（日時）

ここでは、ブログ記事として、以下のデータを持つようにします。

- 投稿者名（user_name）: string
- 投稿日（published_date）: datetime
- タイトル（title）: string
- 内容（content）: text

投稿日は、日付に加え時間も持たせたいので、**datetime**にしています。

### scaffoldの実行

ターミナルで、現在の位置を確認します。以下を入力してください。

```bash
pwd
```

**pwd**はLinuxコマンドです。
{: .notice--info}

現在いる位置が表示されます。

```bash
/home/ubuntu/eastback-blog
```

<figure>
  <img src="{{ '/assets/images/rails/05/pwd.png' | relative_url }}" alt="pwd">
</figure>

もし、違っているのであれば、**cd**コマンドで移動します。

```bash
cd eastback-blog # eastback-blogフォルダへ移動する場合
cd .. # 一つ上のフォルダへ移動する場合
```

ターミナルで、以下を実行してください。

```bash
rails generate scaffold blog user_name:string published_date:datetime title:string content:text
```

<figure>
  <img src="{{ '/assets/images/rails/05/scaffold.png' | relative_url }}" alt="scaffold">
</figure>

実行が終了するまでに、しばらく時間がかかります。

終わったら、データベースを作成します。

ターミナルで、以下を実行してください。

```bash
rails db:migrate
```

<figure>
  <img src="{{ '/assets/images/rails/05/db-migrate.png' | relative_url }}" alt="db:migrate">
</figure>

これで、ブログアプリの完成です。

## ブログアプリの表示

[Railsプロジェクトの作成 - ウェブサーバの確認](){:target="_blank"}と同様に、ウェブサーバを起動して表示させます。

以下を入力してEnterキーを押します。

```bash
rails server
```

<figure>
  <img src="{{ '/assets/images/rails/05/server.png' | relative_url }}" alt="Web Server">
</figure>

ブラウザアイコンをクリックします。ブラウザウィンドウが起動して、Railsのデフォルト画面が表示されます。

<figure>
  <img src="{{ '/assets/images/rails/05/server2.png' | relative_url }}" alt="Web Server">
</figure>

見やすいように、ブラウザウィンドウを拡大表示します。

**scaffold**で作成したアプリを表示させるには、URLの最後に**/blogs**と追加して、Enterキーを押すと表示されます。

**blog**ではなく**blogs**と複数形であることに注意してください。
{: .notice--warning}

<figure>
  <img src="{{ '/assets/images/rails/05/blog.png' | relative_url }}" alt="Blog App">
</figure>

**scaffold**を使うだけで、ウェブアプリが簡単に作成できました。

## ブログアプリの動作確認

まだブログ記事は空です。ブログ記事を登録してみます。

**New Blog**をクリックしてください。

<figure>
  <img src="{{ '/assets/images/rails/05/create-blog.png' | relative_url }}" alt="Create Blog">
</figure>

**New Blog**（新規登録）画面が表示されます。

<figure>
  <img src="{{ '/assets/images/rails/05/create-blog2.png' | relative_url }}" alt="Create Blog">
</figure>

適当に入力してください。入力したら、**Create Blog**ボタンを押してください。

<figure>
  <img src="{{ '/assets/images/rails/05/create-blog3.png' | relative_url }}" alt="Create Blog">
</figure>

登録内容が表示されます。**back**をクリックしてください。

<figure>
  <img src="{{ '/assets/images/rails/05/create-blog4.png' | relative_url }}" alt="Create Blog">
</figure>

最初の画面（ブログ一覧画面）が表示されます。登録した内容が表示されています。

<figure>
  <img src="{{ '/assets/images/rails/05/create-blog5.png' | relative_url }}" alt="Create Blog">
</figure>

同様に、もう一つブログ記事を作成してください。一覧に戻ると、２つ目が表示されています。

<figure>
  <img src="{{ '/assets/images/rails/05/create-blog6.png' | relative_url }}" alt="Create Blog">
</figure>

ブログ記事を編集する場合は、一覧の右側にある**Edit**をクリックします。

**Editting Blog**（編集）画面が表示されます。

<figure>
  <img src="{{ '/assets/images/rails/05/create-blog7.png' | relative_url }}" alt="Create Blog">
</figure>

編集して**Update Blog**ボタンを押すと、登録内容が表示されます。**back**をクリックしてください。

<figure>
  <img src="{{ '/assets/images/rails/05/create-blog8.png' | relative_url }}" alt="Create Blog">
</figure>

ブログ一覧が表示されます。変更した内容が表示されています。

<figure>
  <img src="{{ '/assets/images/rails/05/create-blog9.png' | relative_url }}" alt="Create Blog">
</figure>

ブログ記事を削除する場合は、一覧の右側にある**Destroy**をクリックします。

確認用ダイアログが表示されます。**OK**ボタンを押すと削除され、**キャンセル**ボタンを押すと、削除がキャンセルされます。

<figure>
  <img src="{{ '/assets/images/rails/05/create-blog10.png' | relative_url }}" alt="Create Blog">
</figure>

このように、**scaffold**を使って作成したウェブアプリは、アプリとしての基本的な機能（登録、編集、削除、表示）を持っています。
