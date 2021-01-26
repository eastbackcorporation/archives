---
title: "Rails環境の動作確認"
permalink: /rails/check-rails-app/
toc: true
---
ここでは、Paiza Cloudを使って説明します。

## サーバの作成
[Paiza Cloud](https://paiza.cloud/ja/){:target="_blank"}にログインします。

まだサーバを作成していなければ、以下のような画面が表示されます。

**新規サーバ作成**ボタンを押してください。

<figure>
  <img src="{{ '/assets/images/rails/03/create-server.png' | relative_url }}" alt="Create Server">
</figure>

もし、プラン選択のダイアログが表示された場合は、**無料プラン**の**選択**ボタンを押してください。

<figure>
  <img src="{{ '/assets/images/rails/03/create-server2.png' | relative_url }}" alt="Create Server">
</figure>

料金をお支払いされる場合は、有料プランを選択されても結構です（有料プランの方が快適に利用できます）。
{: .notice--info} 

**サーバ設定**ダイアログが表示されます。

**サーバ名**は自動的に入力されています。変更したい場合は変更して構いません。
**Web開発**の**Ruby on Rails**を選択します。他の項目は選択しなくても結構です。

**新規サーバ作成**ボタンを押します。

<figure>
  <img src="{{ '/assets/images/rails/03/create-server3.png' | relative_url }}" alt="Create Server">
</figure>

開発環境が表示されます。

中央のウィンドウに**チュートリアル**が表示されます。もし興味あれば読んでみてください。必要なければ、ウィンドウ右上のバッテンをクリックして閉じます。

<figure>
  <img src="{{ '/assets/images/rails/03/create-server4.png' | relative_url }}" alt="Create Server">
</figure>


## 開発環境の確認
Paiza Cloudの開発環境は、他の開発環境(Visual Studio Codeなど)と似た構造となっています。

中央左側には、ファイルやフォルダがツリー表示されます。右側には、ファイルやターミナルが表示される領域があります。
また、左端には分かりやすく**新規ファイル**、**ターミナル**、**ブラウザ**ボタンがあり、素早く作成できます。

<figure>
  <img src="{{ '/assets/images/rails/03/create-server5.png' | relative_url }}" alt="Create Server">
</figure>

**新規ファイル**をクリックします。**ファイルを新規作成**ダイアログが表示されます。

<figure>
  <img src="{{ '/assets/images/rails/03/check-env.png' | relative_url }}" alt="Check Env.">
</figure>

ファイル名に**hello.rb**と入力します。

<figure>
  <img src="{{ '/assets/images/rails/03/check-env2.png' | relative_url }}" alt="Check Env.">
</figure>

**作成**ボタンを押します。

ファイルが作成されて、表示されます。

<figure>
  <img src="{{ '/assets/images/rails/03/check-env3.png' | relative_url }}" alt="Check Env.">
</figure>

**hello.rb**ファイルに`puts "Hello World"`と入力して、保存ボタンを押します。

<figure>
  <img src="{{ '/assets/images/rails/03/check-env4.png' | relative_url }}" alt="Check Env.">
</figure>

**ターミナル**をクリックします。ターミナルが表示されます。

<figure>
  <img src="{{ '/assets/images/rails/03/check-env5.png' | relative_url }}" alt="Check Env.">
</figure>

Rubyバージョンの確認と、Rubyプログラムを実行してみます。

**ターミナル**に、`ruby -v`と入力して、Enterキーを押します。Rubyのバージョンが表示されます。

続けて、**ターミナル**に、`ruby hello.rb`と入力して、Enterキーを押します。**ターミナル**に、`Hello World`と表示されます

<figure>
  <img src="{{ '/assets/images/rails/03/check-env6.png' | relative_url }}" alt="Check Env.">
</figure>
