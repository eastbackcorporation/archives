---
title: "Railsプロジェクトの作成"
permalink: /rails/create-rails-project/
toc: true
---
Railsでは、ウェブアプリをプロジェクト単位で管理します。

プロジェクトには、プログラムファイルの他に、ライブラリ管理や、データベース設定など、アプリ全体に関わるファイルが一式入っています。

## プロジェクトの作成
**ターミナル**をクリックします。ターミナルが表示されます。

<figure>
  <img src="{{ '/assets/images/rails/04/terminal.png' | relative_url }}" alt="Terminal">
</figure>

ファイルやターミナルなどのウィンドウは、右上の**□**をクリックすると大きく広がります。もう一度クリックすると元のサイズに戻ります。
{: .notice--info}

これから、プロジェクトを作成します。

プロジェクト名は何でもよいですが、この後**ブログアプリ**を作っていきますので、**?????-blog**というプロジェクト名にします。

**?????**の部分を、自分の名前に置き換えてください。ここでは、**eastback-blog**とします。

ターミナルで、以下を入力してEnterキーを押します。

```bash
rails new eastback-blog
```

<figure>
  <img src="{{ '/assets/images/rails/04/project.png' | relative_url }}" alt="Project">
</figure>

プロジェクト作成に時間がかかる場合があります。
{: .notice--info}

プロジェクト作成が終わると、**eastback-blog**フォルダが作成されます。左側のツリー表示で、フォルダを展開します。

アプリに必要なフォルダやファイルが作成されています。

<figure>
  <img src="{{ '/assets/images/rails/04/project2.png' | relative_url }}" alt="Project">
</figure>

## ウェブサーバの確認
### ウェブサーバの起動
まだウェブアプリは作成していませんが、ウェブサーバを起動してみます。

最初に、プロジェクトフォルダに移動します。

ターミナルで、以下を入力してEnterキーを押します。

```bash
cd eastback-blog
```

プロジェクト名によってフォルダ名が違いますので、フォルダ名に合わせて変えてください。
{: .notice--warning}

<figure>
  <img src="{{ '/assets/images/rails/04/web-server.png' | relative_url }}" alt="Web Server">
</figure>

次に、ウェブサーバを起動します。

以下を入力してEnterキーを押します。

```bash
rails server
```

<figure>
  <img src="{{ '/assets/images/rails/04/web-server2.png' | relative_url }}" alt="Web Server">
</figure>

もし、ターミナルを拡大表示している場合は、左側のボタンを表示させるために、一旦元のサイズに戻します。
{: .notice--info}

しばらくすると、画面左側に`3000`と書かれたブラウザアイコンが追加されます。

<figure>
  <img src="{{ '/assets/images/rails/04/web-server3.png' | relative_url }}" alt="Web Server">
</figure>

このアイコンをクリックします。ブラウザウィンドウが起動して、Railsのデフォルト画面が表示されます。

<figure>
  <img src="{{ '/assets/images/rails/04/web-server4.png' | relative_url }}" alt="Web Server">
</figure>

ブラウザウィンドウの右上の**□**をクリックして、拡大します。

<figure>
  <img src="{{ '/assets/images/rails/04/web-server5.png' | relative_url }}" alt="Web Server">
</figure>

### ウェブサーバの停止
ウェブサーバを停止させます。

ブラウザウィンドウの右上の**□**をクリックして、元のサイズに戻し、右上の**✕**をクリックして閉じます。

<figure>
  <img src="{{ '/assets/images/rails/04/web-server6.png' | relative_url }}" alt="Web Server">
</figure>

次に、ターミナルウィンドウのどこでも良いのでクリックして、ウィンドウをアクティブにしてから、**Ctrl + c**（コントロールキーを押しながらCキー）を押してください。
ターミナルが入力状態に戻ります（ブラウザアイコンも消えます）。

<figure>
  <img src="{{ '/assets/images/rails/04/web-server7.png' | relative_url }}" alt="Web Server">
</figure>
