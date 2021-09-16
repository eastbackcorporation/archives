---
title: "簡単なゲームの作成"
permalink: /dxruby/create-simple-game/
toc: true
---
## simple-gameの作成
簡単なゲーム作成を通して、DXRubyのプログラミングに慣れていきます。

新しく出てきた内容（クラスやメソッドなどの仕様）は、[Rubyのリファレンスマニュアル](https://docs.ruby-lang.org/ja/2.7.0/doc/index.html){:target="_blank"}や、[DXRubyのAPIリファレンス](http://mirichi.github.io/dxruby-doc/api/index.html){:target="_blank"}を見て確認しながら進めると、理解が深まります。
{: .notice--info} 

### ゲーム用フォルダの作成
最初に、プログラムファイルを置くフォルダを作成します。どこのフォルダでプログラムを作成してもよいですが、
ここでは複数のファイルを扱うため、専用のフォルダを作った方が管理しやすいためです。

コマンドプロンプトで、今いる場所が**C:¥ruby_lecture¥code**であることを確認します。
もし違っていたら、**cd**コマンドで移動します。

コマンドプロンプトに以下を入力します。

```bash
mkdir simple-game
```

**simple-game**フォルダが作成されます。

<figure>
  <img src="{{ '/assets/images/dxruby/04/mkdir.png' | relative_url }}" alt="mkdir command">
</figure>

**cd**コマンドで、作成した**simple-game**フォルダに移動します。

コマンドプロンプトに以下を入力します。

```bash
cd simple-game
```

<figure>
  <img src="{{ '/assets/images/dxruby/04/cd-simple-game.png' | relative_url }}" alt="cd command">
</figure>

### プログラムファイルの作成
プログラム用のファイルを作成します。どんなファイル名でもよいですが、ここでは**main.rb**とします。

VSCodeの左側のツリーから、**simple-game**フォルダ上にマウスカーソルを移動させて、右クリックします。
メニューが表示されますので、**新しいファイル**をクリックします。

<figure>
  <img src="{{ '/assets/images/dxruby/04/create-file.png' | relative_url }}" alt="Create File">
</figure>

ファイル名の入力フィールドに、**main.rb**と入力します。

<figure>
  <img src="{{ '/assets/images/dxruby/04/create-file2.png' | relative_url }}" alt="Create File">
</figure>

**main.rb**ファイルが作成され、右側に表示されます。

<figure>
  <img src="{{ '/assets/images/dxruby/04/create-file3.png' | relative_url }}" alt="Create File">
</figure>

### ウィンドウの表示
それでは、プログラムを書いていきます。最初にゲーム画面を表示させるプログラムを書きます。

**main.rb**に以下のコードを書きます。

```ruby
require 'dxruby'

Window.loop do
end
```

**Window**の最初の**W**は大文字です。
{: .notice--info} 

保存して、実行します。

コマンドプロンプトに以下を入力します。

```bash
ruby main.rb
```

<figure>
  <img src="{{ '/assets/images/dxruby/04/program1.png' | relative_url }}" alt="Program">
</figure>

黒いウィンドウが表示されます。

<figure>
  <img src="{{ '/assets/images/dxruby/04/program2.png' | relative_url }}" alt="Program">
</figure>

プログラムを終了させる場合は、ウィンドウ右上のバツをクリックするか、コマンドプロンプトで**Ctrl+C**（コントロールキーを押しながらC）を押します。

少しプログラムを説明をします。

`require 'dxruby'`は、DXRubyライブラリを使いますという宣言です。

`Window.loop do〜end`は、繰り返し処理（ループ）です。DXRubyライブラリの中で定義してあり、ウィンドウを作成して、表示する仕様になっています。
また、このループは、**1秒間に60回**繰り返されます。

DXRubyを使ったプログラムの基本的な書き方は、以下のようになります。

```ruby
require 'dxruby'

# ここに、初期設定（変数の代入、インスタンスの生成など）を書く

Window.loop do
# ここに、データの更新や描画処理などを書く
end
```

ウィンドウのサイズは、デフォルトで**640ピクセルx480ピクセル**です。
{: .notice--info} 

### 文字の描画
画面に文字を表示してみます。

**main.rb**に、**追加**の行を追加します。

```ruby
require 'dxruby'

font = Font.new(32) # 追加

Window.loop do
  Window.draw_font(100, 100, "テスト", font) # 追加
end
```

プログラムを実行します。

<figure>
  <img src="{{ '/assets/images/dxruby/04/font.png' | relative_url }}" alt="Font">
</figure>

ウィンドウに**テスト**が表示されました。

少しプログラムを説明をします。

最初に、**Font**クラスのインスタンスを**font**変数に代入しています。これは、文字のフォントの条件（種類やサイズなど）を設定するもので、
ここでは、フォントサイズを32ピクセルに設定しています。

ループの中では、**Window.draw_font**メソッドを使って、**テスト**を表示させています。
ウィンドウや文字、画像などは、xとyを使って位置を表します。向かって左上が原点(0, 0)で、右下に行くほど数字が増えていきます。
このコードでは、ウィンドウの(100, 100)の位置に、**テスト**文字の(0, 0)（左上）がくるように、表示させています。

次に、ループの繰り返しごとに数字を1ずつ増やして表示するプログラムに書き換えます。

**main.rb**を、以下のように書き換えてください。

```ruby
require 'dxruby'

font = Font.new(32)
count = 1 # 追加

Window.loop do
  Window.draw_font(100, 100, "ループ回数：#{count}", font) # 書き換え
  count = count + 1 # 追加
end
```

プログラムを実行します。

<figure>
  <img src="{{ '/assets/images/dxruby/04/font2.png' | relative_url }}" alt="Font">
</figure>

ウィンドウにループ回数が表示されました。目まぐるしく増えていきますね。


### 画像の描画
画面に画像を表示してみます。

画像ファイルは、[こちら](https://download.eastback.co.jp/dxruby/image.zip){:target="_blank"}からダウンロードしてください。

ダウンロードした**image.zip**ファイルを展開して、imageフォルダ内にある**image**フォルダを、**simple-game**フォルダ内に移動させてください。

**main.rb**を、以下のように書き換えてください（文字の部分は削除します）。

```ruby
require 'dxruby'

player_img = Image.load("image/player.png")

Window.loop do
  Window.draw(100, 100, player_img)
end
```

プログラムを実行します。

<figure>
  <img src="{{ '/assets/images/dxruby/04/image.png' | relative_url }}" alt="Image">
</figure>

文字の場合と同様、ウィンドウの(100, 100)の位置に画像が表示されました（粗末な画像ですみません）。

プログラムの書き方は、文字の場合と若干異なりますが、同じような処理を行っています。

次に、プログラムを、画面右方向に1ループで1ピクセル移動するように書き換えます。

**main.rb**を、以下のように書き換えてください。

```ruby
require 'dxruby'

player_img = Image.load("image/player.png")
x = 100 # 追加

Window.loop do
  Window.draw(x, 100, player_img) # 書き換え
  x = x + 1 # 追加
end
```

プログラムを実行します。

<figure>
  <img src="{{ '/assets/images/dxruby/04/image2.png' | relative_url }}" alt="Image">
</figure>

画像が右方向に動くのが分かります。つまり、ループ内の処理で描画したものを、次のループでは一旦消して、再度描画していることが分かります。

### キーボード入力
キーボードからの入力を反映させるようにします。

**main.rb**を、以下のように書き換えてください。

```ruby
require 'dxruby'

player_img = Image.load("image/player.png")
x = 100
y = 100 # 追加

Window.loop do
  x = x + Input.x # 追加
  y = y + Input.y # 追加
  Window.draw(x, y, player_img) # 書き換え
end
```

プログラムを実行します。

キーボードの矢印キーを押してみてください。

<figure>
  <img src="{{ '/assets/images/dxruby/04/image3.png' | relative_url }}" alt="Image">
</figure>

画像が上下左右に動くようになりました。プログラム中の**Input.x**は、右矢印キーが押されると、整数**1**を返し、左矢印キーが押されると整数**-1**を返します。
**Input.y**については、みなさん想像できるでしょう。

### Spriteクラス
DXRubyを使ったゲームを作成する上で、重要になるのが**Sprite**クラスです。

ゲームでは、プレイヤー、敵、弾やビームなどの武器、障害物などが出てきます。そして、それらが当たったかどうかで、ゲームの流れが変わってきます。
当たったかどうかの判定は、基本的に画像の位置関係から判断します。しかし、その処理をプログラミングしようとしたら、結構手間がかかります。

**Sprite**クラスには、衝突判定の処理があらかじめ用意されているため、それを使うことで、比較的簡単にプログラムを書くことができます。

まず最初に、**Sprite**クラスに画像を設定します。

**main.rb**を、以下のように書き換えてください。

```ruby
require 'dxruby'

player_img = Image.load("image/player.png")
x = 100
y = 100
player = Sprite.new(x, y, player_img)

Window.loop do
  player.x += Input.x
  player.y += Input.y
  player.draw
end
```

プログラムを実行します。

キーボードの矢印キーを押してみてください。前のプログラムと同じように、プレイヤーを動かすことができます。

プログラムの説明をします。

- **Sprite**クラスは、**new**メソッドを使って、インスタンスを生成します。引数には、位置と画像を渡しています。
- **Sprite**クラスには、x、yが外部から参照・変更できるようになっているので、ループの中で位置を更新しています。
- **Sprite**クラスには、描画メソッド**draw**が定義されています。
- **player.x += Input.x**の書き方は初めて見ると思います。`a = a + n`の短縮形が`a += n`です。

上記では、直接**Sprite**クラスを使用しました。ただ、独自の処理を書きたい場合、このままではできません。
そこで、Rubyの**継承**を使います。**継承**を使うと、既存のクラス定義（変数やメソッドなど）を引き継いだ、新しいクラスを自分で定義することができます。

**継承**の書き方は、以下のようになります。

```ruby
class 新しいクラス名 < 既存クラス名
  def メソッド名
    処理
  end
  ・・・
end 
```

上記の、**既存クラス**を**スーパークラス（親クラス）**、**新しいクラス**を**サブクラス（子クラス）**と言います。
{: .notice--info}

**新しいクラス**では、**既存クラス**のメソッドを使うことができます。また、**新しいクラス**定義内で、独自のメソッドを定義することができます。さらに、**既存クラス**のメソッドと同じ名前のメソッド定義を書くと、**既存クラス**のメソッドを上書き（オーバーライド）することもできます。

それでは、**Sprite**クラスを継承した、プレイヤー用のクラス**Player**を作ります。

**main.rb**を、以下のように書き換えてください。

```ruby
require 'dxruby'

class Player < Sprite
  def update
    self.x += Input.x
    self.y += Input.y
  end
end

player_img = Image.load("image/player.png")
x = 100
y = 100
player = Player.new(x, y, player_img)

Window.loop do
  player.update
  player.draw
end
```

プログラムを実行します。

キーボードの矢印キーを押してみてください。前のプログラムと同じように、プレイヤーを動かすことができます。

Playerクラスの定義で、プレイヤーの位置を更新するための**update**メソッドを追加しています。これにより、ループ内のコードが簡潔になります。

次に、衝突判定の機能を追加します。

**Sprite**クラスには、衝突判定用のメソッド**Sprite.check**が定義されています。
このメソッドは、衝突しているか判定し、もし衝突していたら、**hit**メソッド、**shot**メソッドを呼びます。

```ruby
require 'dxruby'

class Player < Sprite
  def update
    self.x += Input.x
    self.y += Input.y
  end
end

class Enemy < Sprite
  def hit
    self.vanish
  end
end

player_img = Image.load("image/player.png")
x = 100
y = 100
player = Player.new(x, y, player_img)

enemy_img = Image.load("image/enemy.png")
x = 300
y = 300
enemy = Enemy.new(x, y, enemy_img)

Window.loop do
  player.update
  player.draw

  enemy.draw

  Sprite.check(player, enemy)
end
```

プログラムを実行します。

プレイヤー（善）、と敵（悪）が表示されます。キーボードの矢印キーを押してプレイヤーを移動させて、敵に体当たりしてみてください。敵が消えます。

<figure>
  <img src="{{ '/assets/images/dxruby/04/sprite.png' | relative_url }}" alt="Sprite">
</figure>

プログラムの説明をします。

- **Player**クラスと同様に**Sprite**クラスを継承した**Enemy**クラスを定義しています。
- **Enemy**クラスの**hit**メソッドは、衝突した時に呼ばれるメソッドです。
- **vanish**メソッドは、**Sprite**のインスタンスを消します（描画できなくします）。この場合、自分自身（敵）を消します。
- ループの中では、敵の描画と衝突判定のコードを追加しています。

### ファイル分割
プログラムコードが長くなってきました。
一つのプログラムファイルにまとめて書いてもよいですが、長くなればなるほど、可読性が損なわれていきます。

そこで、ファイルを分割してみます。通常、クラスごとにファイルを分け、ファイル名にはクラス名を（小文字で）使います。

以下のように、ファイルを分割します。

**player.rb**
```ruby
class Player < Sprite
  def update
    self.x += Input.x
    self.y += Input.y
  end
end
```

**enemy.rb**
```ruby
class Enemy < Sprite
  def hit
    self.vanish
  end
end
```

**main.rb**
```ruby
require 'dxruby'

require_relative 'player'
require_relative 'enemy'

player_img = Image.load("image/player.png")
x = 100
y = 100
player = Player.new(x, y, player_img)

enemy_img = Image.load("image/enemy.png")
x = 300
y = 300
enemy = Enemy.new(x, y, enemy_img)

Window.loop do
  player.update
  player.draw

  enemy.draw

  Sprite.check(player, enemy)
end
```

<figure>
  <img src="{{ '/assets/images/dxruby/04/split-files.png' | relative_url }}" alt="Split Files">
</figure>

**main.rb**には、他のプログラムファイルを**require_relative**構文を使って読み込みます（拡張子**.rb**は不要です）。

プログラムの実行は、これまでと同じ`ruby main.rb`です。

キーボードの矢印キーを押してみてください。前のプログラムと同じ動きをします。


### 配列を使う
敵が1体ではおもしろくないので、増やしてみます。

**main.rb**を、以下のように書き換えてください。

**main.rb**
```ruby
require 'dxruby'

require_relative 'player'
require_relative 'enemy'

player_img = Image.load("image/player.png")
enemy_img = Image.load("image/enemy.png")

player = Player.new(100, 100, player_img) # 簡潔にする
enemies = [] # 書き換え、以下追加
10.times do
  enemies << Enemy.new(rand(0..(640 - 32 - 1)), rand((480 - 32 - 1)), enemy_img)
end

Window.loop do
  player.update
  player.draw

  Sprite.draw(enemies)

  Sprite.check(player, enemies) # 書き換え
end
```

プログラムを実行します。

敵（悪）が10体表示されます。同様にキーボードの矢印キーを押してプレイヤーを移動させて、すべての敵に体当たりしてみてください。

<figure>
  <img src="{{ '/assets/images/dxruby/04/split-files2.png' | relative_url }}" alt="Split Files">
</figure>

プログラムの説明をします。

- **enemies**変数に空の配列を作って、**Emeny**クラスのインスタンスを挿入しています。
- **整数.times do〜end**の**times**は、整数クラス（Integer）に定義されているメソッドで、整数回ループを回します。
- **Enemy**クラスのインスタンス生成時、敵画像がウィンドウをはみ出さないxとyを**rand**メソッドを使ってランダムに設定しています。
- **Sprite.check**メソッドは、引数に配列を渡すことができます。

### インスタンス変数
体当たりした敵の数を表示するようにします。

**player.rb**と**main.rb**を、以下のように書き換えてください。

**player.rb**
```ruby
class Player < Sprite
  attr_accessor :score # 追加

  def initialize(x, y, image) # 追加
    @score = 0
    super
  end

  def update
    self.x += Input.x
    self.y += Input.y
  end

  def shot # 追加
    @score += 1
  end
end
```

**main.rb**
```ruby
require 'dxruby'

require_relative 'player'
require_relative 'enemy'

font = Font.new(32) # 追加
player_img = Image.load("image/player.png")
enemy_img = Image.load("image/enemy.png")

player = Player.new(100, 100, player_img)
enemies = []
10.times do
  enemies << Enemy.new(rand(0..(640 - 32 - 1)), rand((480 - 32 - 1)), enemy_img)
end

Window.loop do
  player.update
  player.draw

  Sprite.draw(enemies)
  Window.draw_font(10, 10, "スコア：#{player.score}", font) # 追加

  Sprite.check(player, enemies)
end
```

プログラムを実行します。

スコアが表示されます。キーボードの矢印キーを押してプレイヤーを移動させて、敵に体当たりすると、スコアが加算されます。

<figure>
  <img src="{{ '/assets/images/dxruby/04/array.png' | relative_url }}" alt="Split Files">
</figure>

プログラムの説明をします。

- **Player**クラスに、スコアを格納する**@score**変数を追加しました。
- **Player**クラスに、**shot**メソッドを追加しました。衝突判定で、衝突した時にスコアをカウントアップします。
- **main.rb**のループの中に、スコアを表示する機能を追加しました。

衝突判定で、衝突した時に**shot**メソットと**hit**が呼ばれます。
**Sprite**クラスの**check**メソッドで、第1引数の方には、**shot**メソッド、第2引数の方には、**hit**メソッドが呼ばれる仕様です。
{: .notice--info} 

### 整数の演算
ゲーム性を持たせるために、残り時間を表示し、ゼロになったらプレイヤーの動きを止めます。

**main.rb**を、以下のように書き換えてください。

**main.rb**
```ruby
require 'dxruby'

require_relative 'player'
require_relative 'enemy'

font = Font.new(32)
player_img = Image.load("image/player.png")
enemy_img = Image.load("image/enemy.png")

player = Player.new(100, 100, player_img)
enemies = []
10.times do
  enemies << Enemy.new(rand(0..(640 - 32 - 1)), rand((480 - 32 - 1)), enemy_img)
end

timer = 600 + 60 # 追加

Window.loop do
  if timer >= 60 # 追加
    timer -= 1 # 追加
    player.update
  end

  player.draw

  Sprite.draw(enemies)
  Window.draw_font(10, 0, "スコア：#{player.score}", font)
  Window.draw_font(10, 32, "残り時間：#{timer / 60}秒", font) # 追加

  Sprite.check(player, enemies)
end
```

プログラムを実行します。

残り時間がカウントダウンしていき、ゼロになったらプレイヤーが動かなくなります。

<figure>
  <img src="{{ '/assets/images/dxruby/04/integer.png' | relative_url }}" alt="Split Files">
</figure>

プログラムの説明をします。

**Window.loop**は、1秒間に60回ループします。この特性を利用して、残り時間を算出します。

Rubyでは、**整数どうしの計算結果は整数**というルールがあります。ちなみに、**実数どうしの計算、実数と整数の計算は実数**になります。
つまり、`600 / 60`の結果は`10`ですが、`599 / 60`の結果は`9.98333`ではなく、切り捨てられて`9`となります。
ここでは、そのRubyの仕様を利用して、残り時間を秒で表示しています。

### カスタマイズ
単純ですが、ゲームらしくなってきました。

もっと楽しめるゲームにするには、どんな機能があったらよいでしょうか。考えてみてください。
