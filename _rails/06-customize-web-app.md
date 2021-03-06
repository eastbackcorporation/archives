---
title: "アプリのカスタマイズ"
permalink: /rails/customize-web-app/
toc: true
---
## ブログアプリをカスタマイズ

Railsの**scaffold**は、非常に強力な機能で、
ウェブサービスで必要な基本的な機能（データ登録、編集、削除、個別表示、一覧表示）を
コマンド１つで作成する事ができます。

ただ、そのままではシンプルな機能しかありませんし、見た目も寂しいです。

ここでは、簡単なカスタマイズのやり方を紹介します。

### ウェブサーバの起動

カスタマイズの内容をリアルタイムで確認するために、ウェブサーバを起動して、ブログアプリを表示させます。

ターミナルを起動します。

以下のように、**pwd**コマンドを入力して、**場所**を確認します。

```bash
~/eastback-blog$ pwd
/home/ubuntu/eastback-blog
~/eastback-blog$
```

<figure>
  <img src="{{ '/assets/images/rails/06/pwd.png' | relative_url }}" alt="pwd">
</figure>

アプリのフォルダにいることを確認してください。もし違う場所であれば、**cd**コマンドで移動してください。

ウェブブラウザを起動します。以下を実行してください。

```bash
rails server
```

<figure>
  <img src="{{ '/assets/images/rails/06/rails-server.png' | relative_url }}" alt="Rails Server">
</figure>

ブラウザアイコンをクリックして、ブラウザウィンドウを起動します。

<figure>
  <img src="{{ '/assets/images/rails/06/rails-server2.png' | relative_url }}" alt="Rails Server">
</figure>

<figure>
  <img src="{{ '/assets/images/rails/06/rails-server3.png' | relative_url }}" alt="Rails Server">
</figure>

ブラウザのURLの最後に**/blogs**を追加して、Enterキーを押します。ブログアプリが表示されます。

<figure>
  <img src="{{ '/assets/images/rails/06/rails-server4.png' | relative_url }}" alt="Rails Server">
</figure>

## パスのカスタマイズ

今のところ、ブログアプリを表示させるには、URLの最後に**/blogs**を追加する必要があります。

この部分なしで表示できるように変更します。

左側のツリーから`/app/config/routes.rb`ファイルをダブルクリックして開きます。

<figure>
  <img src="{{ '/assets/images/rails/06/routes.png' | relative_url }}" alt="Routes">
</figure>

1行目の後に以下の行を挿入してください。

```ruby
root to: "blogs#index"
```

<figure>
  <img src="{{ '/assets/images/rails/06/routes2.png' | relative_url }}" alt="Routes">
</figure>

URLの最後の**/blogs**を削除して、Enterキーを押します。ブログアプリが表示されます。

<figure>
  <img src="{{ '/assets/images/rails/06/routes3.png' | relative_url }}" alt="Routes">
</figure>

このように、**routes.rb**は、Rails内の機能とURLパスを結びつける設定を記述するためのファイルです。

## デザインのカスタマイズ

Railsはウェブアプリなので、他のウェブサイトと同様に、HTMLとCSS（とJavascript）でデザインをカスタマイズすることができます。

ここでは、有名なCSSフレームワーク[Bootstrap](https://getbootstrap.jp/){:target="_blank"}[^1]を使って、デザインをカスタマイズします。

[^1]: Twitter社によって開発されました。

RailsでBootstrapを利用する方法はいくつかあります（特にRailsバージョン6は、Webpackerが導入されたため、利用方法が変わりました）。ここでは、[Bootstrap 4.3](https://getbootstrap.jp/docs/4.3/getting-started/introduction/){:target="_blank"}のドキュメントに従ってシンプルな方法で行います。
{: .notice--info} 

### Bootstrapの導入
左側のツリーから`/app/views/layouts/application.html.erb`ファイルをダブルクリックして開きます。

<figure>
  <img src="{{ '/assets/images/rails/06/design.png' | relative_url }}" alt="Design">
</figure>

8、9行目
```html
<%= stylesheet_link_tag 'application', media: 'all', 'data-turbolinks-track': 'reload' %>
<%= javascript_pack_tag 'application', 'data-turbolinks-track': 'reload' %>
```

を削除して、以下に書き換えます。

```html
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
```

<figure>
  <img src="{{ '/assets/images/rails/06/design2.png' | relative_url }}" alt="Design">
</figure>

### コンテンツへの適用

15行目
```html
<%= yield %>
```

を削除して、以下に書き換えます。

```html
<div class="container">
  <%= yield %>
</div>
```

<figure>
  <img src="{{ '/assets/images/rails/06/design3.png' | relative_url }}" alt="Design">
</figure>

ブラウザウィンドウをリロードすると、ブログアプリのデザインが若干変化します。

<figure>
  <img src="{{ '/assets/images/rails/06/design4.png' | relative_url }}" alt="Design">
</figure>

14行目の`<body>`のすぐ後に、以下を挿入します。

```html
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="/">イーストバックブログ</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item active">
        <a class="nav-link" href="/">ブログ <span class="sr-only">(current)</span></a>
      </li>
    </ul>
  </div>
</nav>
```

<figure>
  <img src="{{ '/assets/images/rails/06/design5.png' | relative_url }}" alt="Design">
</figure>

上記の2行目**イーストバック　ブログ**の部分を、それぞれのブログのタイトルに変更してください。
{: .notice--info}

ブラウザウィンドウをリロードすると、上の部分にタイトルが表示されます。

また、レスポンシブル（ブラウザの幅が変わっても、それに対応してデザインが変化する：スマホ対応）になっています。

<figure>
  <img src="{{ '/assets/images/rails/06/design6.png' | relative_url }}" alt="Design">
</figure>

## 機能の追加

### ブログ機能の検討

ブログの登録、編集、削除などはできるようになっていますが、
その他にどんな機能があると、より魅力的なブログアプリになるでしょうか。

- 画像が添付できる。
- ユーザごとにブログを作成できる（ログイン、ユーザ管理）
- ブログにコメントを書き込める。
- ランキング表示

### 画像添付機能の追加

Railsで画像を扱うためのライブラリ（アプリ）は多数ありますが、
ここでは、Railsバージョン5.2から組み込まれた**Active Storage**を利用します。

ターミナルで、一旦ウェブサーバを停止させます。

ターミナル上で、**Ctrl+C**を押してください。

**Ctrl+C**は、**コントロールキー**を押しながら**Cキー**を押すという意味です。
{: .notice--info} 

<figure>
  <img src="{{ '/assets/images/rails/06/activestorage.png' | relative_url }}" alt="Active Storage">
</figure>

ターミナルに以下のコマンドを入力します。

```bash
rails active_storage:install
```

<figure>
  <img src="{{ '/assets/images/rails/06/activestorage2.png' | relative_url }}" alt="Active Storage">
</figure>

続いて、以下のデータベース作成コマンドを入力します。

```bash
rails db:migrate
```

<figure>
  <img src="{{ '/assets/images/rails/06/activestorage3.png' | relative_url }}" alt="Active Storage">
</figure>

これで、Railsの機能**Active Storage**を使う準備ができました。

次に、ブログアプリに画像保存用のデータ**image**を作成します。

ターミナルに以下のコマンドを入力します。

```bash
rails generate migration AddImageToBlogs image:attachment
```

<figure>
  <img src="{{ '/assets/images/rails/06/activestorage4.png' | relative_url }}" alt="Active Storage">
</figure>

続いて、以下のデータベース作成コマンドを入力します。

```bash
rails db:migrate
```

<figure>
  <img src="{{ '/assets/images/rails/06/activestorage5.png' | relative_url }}" alt="Active Storage">
</figure>

左側のツリーから`/app/controllers/blogs_controller.rb`ファイルをダブルクリックして開きます。

67行目

```ruby
params.require(:blog).permit(:user_name, :published_date, :title, :content)
```

<figure>
  <img src="{{ '/assets/images/rails/06/activestorage6.png' | relative_url }}" alt="Active Storage">
</figure>

を、以下の様に書き換えます（:imageを追加）。

```ruby
params.require(:blog).permit(:user_name, :published_date, :title, :content, :image)
```

<figure>
  <img src="{{ '/assets/images/rails/06/activestorage7.png' | relative_url }}" alt="Active Storage">
</figure>

左側のツリーから`/app/models/blogs.rb`ファイルをダブルクリックして開きます。

以下を、

```ruby
class Blog < ApplicationRecord
end
```

<figure>
  <img src="{{ '/assets/images/rails/06/activestorage8.png' | relative_url }}" alt="Active Storage">
</figure>

以下の様に書き換えます（間に1行追加）。

```ruby
class Blog < ApplicationRecord
  has_one_attached :image
end
```

<figure>
  <img src="{{ '/assets/images/rails/06/activestorage9.png' | relative_url }}" alt="Active Storage">
</figure>

左側のツリーから`/app/views/blogs/_form.html.erb`ファイルをダブルクリックして開きます。

<figure>
  <img src="{{ '/assets/images/rails/06/activestorage10.png' | relative_url }}" alt="Active Storage">
</figure>

33行目の下に、以下を追加します。

```ruby
<div class="field">
  <%= form.label :image %>
  <%= form.file_field :image %>
</div>
```

<figure>
  <img src="{{ '/assets/images/rails/06/activestorage11.png' | relative_url }}" alt="Active Storage">
</figure>

左側のツリーから`/app/views/blogs/show.html.erb`ファイルをダブルクリックして開きます。

<figure>
  <img src="{{ '/assets/images/rails/06/activestorage12.png' | relative_url }}" alt="Active Storage">
</figure>

22行目の下に、以下を追加します。

```ruby
<% if @blog.image.attached? %>
  <p>
    <strong>Image:</strong>
    <%= image_tag @blog.image %>
  </p>
<% end %>
```

<figure>
  <img src="{{ '/assets/images/rails/06/activestorage13.png' | relative_url }}" alt="Active Storage">
</figure>

ウェブブラウザを起動します。以下を実行してください。

```bash
rails server
```

<figure>
  <img src="{{ '/assets/images/rails/06/activestorage14.png' | relative_url }}" alt="Active Storage">
</figure>

ウェブブラウザを開きます。

<figure>
  <img src="{{ '/assets/images/rails/06/activestorage15.png' | relative_url }}" alt="Active Storage">
</figure>

**New Blog**リンクをクリックして、ブログの新規作成を行います。

<figure>
  <img src="{{ '/assets/images/rails/06/activestorage16.png' | relative_url }}" alt="Active Storage">
</figure>

**Image**では、画像ファイルを選択します。

<figure>
  <img src="{{ '/assets/images/rails/06/activestorage17.png' | relative_url }}" alt="Active Storage">
</figure>

**Create Blog**ボタンを押して作成すると、添付した画像が表示されます。

<figure>
  <img src="{{ '/assets/images/rails/06/activestorage18.png' | relative_url }}" alt="Active Storage">
</figure>
